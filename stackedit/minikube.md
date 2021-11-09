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
minikube start --mount --mount-string="$HOME/:$HOME/"
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTk1MDc2NzIzNCwxNjg2NjI4MzU1LC0yMj
IzMjI5MDAsMjAwNjg0ODYwMiwxMzk2NjE3MTYyLDM3NTE3MjQ2
Ml19
-->