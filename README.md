
# Kustomize and Kubernetes Project

![Kustomize](https://img.shields.io/badge/Kustomize-5D87BF?logo=kubernetes&logoColor=white&style=flat)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white&style=flat)
![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?logo=kubernetes&logoColor=white&style=flat)
![License](https://img.shields.io/badge/License-MIT-yellow)

This project demonstrates how to manage **Kubernetes** manifests using **Kustomize**. It provides a clean and scalable way to customize Kubernetes deployments across multiple environments without modifying the original YAML files. The project showcases how to manage Kubernetes resources efficiently without templating by leveraging overlays, patches, reusable base configurations, and environment-specific customizations.

<https://kustomize.io/>

<https://kubernetes.io/docs/home/>

---

## Check your version of kubectl

```
kubectl version
```

**If you have 1.21 or above of kubectl you will have access to kubectl kustomize which is the recommended method. If you aren't on version 1.21 or above, upgrade kubectl.**

**You could also download/use the 'kutomize' binary seperatly but the cmds are different.**

## Viewing Kustomize Configs - (Using kubectl kustomize integration)

```
kubectl kustomize .
kubectl kustomize overlays/dev/
kubectl kustomize overlays/prod/
```

## Applying Kustomize Configs - (Using kubectl kustomize integration)

```
kubectl apply -k .
kubectl apply -k overlays/dev/
kubectl apply -k overlays/prod/
```

**Note: if you get field is immutable error, check your configuration and try deleting the resources then applying again.**

## Creating Namespaces if you dont have them already

```
kubectl create namespace dev
kubectl create namespace prod
```

## Accessing the application

```
minikube service kustom-mywebapp-v1
minikube service kustom-mywebapp-v1 -n dev
minikube service kustom-mywebapp-v1 -n prod
```

## References

https://github.com/kubernetes-sigs/kustomize/blob/master/README.md
https://kubectl.docs.kubernetes.io/guides/config_management/offtheshelf/

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

**Star this repository if it helped you!**
