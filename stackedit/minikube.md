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
# brew install docker-compose-completion
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjAwNjg0ODYwMiwxMzk2NjE3MTYyLDM3NT
E3MjQ2Ml19
-->