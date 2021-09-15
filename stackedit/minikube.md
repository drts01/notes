# Minikube

## MacOS

```bash
brew install hyperkit
brew install minikube
brew install kubernetes-cli
echo 'source <(kubectl completion zsh)' >> "~/.zshrc"
```

```bash
minikube config set driver hyperkit
minikube config set container-runtime cri-o
minikube start
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTY4NjYyODM1NSwtMjIyMzIyOTAwLDIwMD
Y4NDg2MDIsMTM5NjYxNzE2MiwzNzUxNzI0NjJdfQ==
-->