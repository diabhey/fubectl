# Fork of [fubectl](https://github.com/kubermatic/fubectl) - Microk8s Saga
Because it's fancy-micork8s.kubectl!

## Prerequisites?
* [fzf](https://github.com/junegunn/fzf)
* [microk8s](https://microk8s.io/)
* [jq](https://stedolan.github.io/jq/)

## Installation

You can directly download the [`mfubectl.source`](https://raw.githubusercontent.com/diabhey/fubectl/master/mfubectl.source) and save it in some directory.

Download:
```bash
curl -LO https://raw.githubusercontent.com/diabhey/fubectl/master/mfubectl.source
```

```bash
# Then add to your .bashrc/.zshrc file:

[ -f <path-to>/mfubectl.source ] && source <path-to>/mfubectl.source

```

## What can it do?

### mk - alias for microk8s.kubectl

Like g for git but 133% more effective!

Examples:
 - `mk get nodes`
 - `mk get pods`
 - `mk version --short`

Usage:
![kGif](./demo_src/k.gif)

---

### mkw - alias for 'watch microk8s.kubectl'


Examples:
 - `mkw nodes`
 - `mkw pods`
 - `mkw nodes,pods,services`

---

### mkall - All pods in all namespaces

Get all pods

Usage:
![kGif](./demo_src/kall.gif)

---

### mkwall - Watch all pods in all namespaces

Watch all pods in all namespaces every 2 seconds.

Usage:
![kGif](./demo_src/kwall.gif)

---

### mkdes - Describe a resource

Examples:
- `mkdes pod`
- `mkdes service`
- `mkdes nodes`

Usage:
![kGif](./demo_src/kdes.gif)

---

### mkdel - Delete a resource

Examples:
- `mkdel pod`
- `mkdel secret`
- `mkdel pvc`

Usage:
![kGif](./demo_src/kdel.gif)

---

### mklog - Print the logs for a container in a pod

Examples:
- `mklog` - Print the last 10 lines
- `mklog 100` - Print the last 100 lines
- `mklog 250 -f` - Print the last 250 lines and follow the output, like `tail -f`
- `mklog 50 -p` - Print the last 50 lines of the previous container

Usage:
![kGif](./demo_src/klog.gif)

---

### mkex - Execute a command in a container

Examples:
- `mkex bash` - Start a bash in a container
- `mkex date` - Print the date in a container

Usage:
![kGif](./demo_src/kex.gif)

---

### mkfor - Forward one or more local ports to a pod

Examples:
- `mkfor 8000` - Forwards port 8000 to a pod
- `mkfor 8000:80` Fowards local port 8000 to a pod's port 80

Usage:
![kGif](./demo_src/kfor.gif)

---

### mksearch - Search for string in resources

Examples:
- `// TODO`

Usage:
![kGif](./demo_src/ksearch.gif)

---

### mkcl - Displays one or many contexts from the kubeconfig file
Context list

Usage:
![kGif](./demo_src/kcl.gif)
---
### mkcs - Sets the current context

Usage:
![kGif](./demo_src/kcs.gif)

---

### kcns - Switch the default namespace

`mkcns` - Set the current default namespace from list
`mkcns kube-system` - Set kube-system as default namespace immediately

Usage:
![kGif](./demo_src/kcns.gif)
---

### mkdebug - Start a debugging Pod in a Cluster

Usage:
![kGif](./demo_src/kdebug.gif)

---

### mkp - Open the Kubernetes dashboard

Opens `localhost:8001/ui` in your browser and runs `microk8s.kubectl proxy`

---

## Extra!
Do you wan't to have the current kubecontext in your prompt?:
```bash
export PS1="\[$(mkube_ctx_name)\] $PS1"
```

for the current namespace (this is currently slow, because it calls microk8s.kubectl every time):
```bash
export PS1="\[$(mkube_ctx_namespace)\] $PS1"
```