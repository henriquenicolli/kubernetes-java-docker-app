APP JAVA KUBERNETES DEPLOY

	Sequencia de comandos para criar uma imagem docker, subir o cluster Kubernetes localmente usando minikube, por fim realizar um deploy de um app java no cluster Kubernetes.

		CRIAR IMAGEM DOCKER
		- docker build -t hnicolli/kubernetes:v1 .


		MONTAR IMAGEM DOCKER
		- docker run -it -p 8080:8080 hnicolli/kubernetes:v1

		Montar um cluster kubernetes local usando o minikube
		https://kubernetes.io/docs/tasks/tools/install-minikube/.

		Subir o minikube
		- minikube start
		- eval $(minikube docker-env)

		Habilitar o dashboard do Kubernetes
		- minikube dashboard

		Criar um deployment
		- kubectl create deployment kubernetes --image=hnicolli/kubernetes:v1

		Expoe o container criado
		- kubectl expose deployment kubernetes --type=LoadBalancer --port=8080

		Verifica o ip do conteiner criado
		- minikube service kubernetes

		Escalar o container
		- kubectl scale -n default deployment kubernetes --replicas=10



