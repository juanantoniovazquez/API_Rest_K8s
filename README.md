# API_Rest_K8s

Para la ejecución correcta se necesitarán los siguietnes comandos:

Para la correcta comunicación entre los puertos del host y el servicio de la aplicación.
kubectl port-forward svc/springboot-service 8080:8080

Para crear el tunel
minikube tunnel
