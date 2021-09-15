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
brew install kubernetes-cli
source <(kubectl completion zsh)

# to-do: enable shell autocompletion
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwOTY2MjgzNDEsLTIyMjMyMjkwMCwyMD
A2ODQ4NjAyLDEzOTY2MTcxNjIsMzc1MTcyNDYyXX0=
-->