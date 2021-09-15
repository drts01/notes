# Minikube

## MacOS

### Server

```bash
brew install hyperkit
brew install minikube
```

```bash
minikube config set driver hyperkit
minikube config set container-runtime cri-o
```

```bash
minikube start
```

### Client

```bash
# brew install docker
# pipx install docker-compose
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTM5NjYxNzE2MiwzNzUxNzI0NjJdfQ==
-->