Primeiro Chart

https://helm.sh/docs/chart_template_guide/getting_started/


Criar o chart

> helm create meuchart


![Panel](https://i.ibb.co/M1tTLGL/image.png)


- NOTES.txt: Texto de ajuda para o seu Chart. É exibido para os usuários quando o mesmo
for instalado.

- deployment.yaml: Um manifesto básico para a criação de uma implantação no
Kubernetes

- service.yaml: Um manifesto básico para a criação de um serviço para a sua implantação
_herlpers.tpl: Lugar para colocar templates auxiliares que podemos reutilizar em todo o
chart


Removendo arquivos
> rm -rf meuchart/templates/*


Criar template
> vim meuchart/templates/configmap.yaml

```
apiVersion: v1
kind: ConfigMap
metadata:
 name: meuchart-configmap
data:
 myvalue: "Hello World"

```

Instalando o chart
> helm install meuchart-v1 ./meuchart

Verificando recursos criados
> helm get manifest meuchart-v1

Removendo chart
> helm uninstall meuchart-v1

Adicionando um objeto
 
```
apiVersion: v1
kind: ConfigMap
metadata:
 name: {{ .Release.Name }}-configmap
data:
 myvalue: "Hello World"
```


Os objetos nos templates são representados por dois pares de chaves ({{ e }} )
Instalando o chart

> helm install meuchart-v2 ./meuchart

Verificando recursos criados
> helm get manifest meuchart-v2

Removendo chart
> helm uninstall meuchart-v2

Testando a instalação
> helm install --debug --dry-run meuchart-v3 ./meuchart


--dry-run: Usado para simular a implantação de um chart. Isso não indica irá aplicar sem
problema.