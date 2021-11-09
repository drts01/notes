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

when replace Docker Desktop:
```bash
minikube config set driver hyperkit
minikube config set container-runtime docker
minikube start --mount --mount-string="$HOME/:$HOME/"
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc2MDI1NDM4LDE2ODY2MjgzNTUsLTIyMj
MyMjkwMCwyMDA2ODQ4NjAyLDEzOTY2MTcxNjIsMzc1MTcyNDYy
XX0=
-->