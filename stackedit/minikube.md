# Minikube

## MacOS

### Server

```sh
brew install hyperkit
brew install minikube
```

```sh
minikube config set driver hyperkit
minikube config set container-runtime cri-o
```

```sh
minikube start
```

### Client

```sh
brew install docker
pipx install docker-compose
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMzc1MTcyNDYyXX0=
-->