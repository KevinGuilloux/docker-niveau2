## k3s

- `wget https://github.com/k3s-io/k3s/releases/download/v1.27.2%2Bk3s1/k3s` download k3s locally 

- `chmod +x k3s && mv k3s /usr/local/bin/` k3s executable and in PATH

- `sudo k3s server &` launch k3s server

- `vagrant ssh box01 -- sudo k3s agent --server https://192.168.56.1:6443 --flannel-iface eth1 --token ${NODE_TOKEN}`  add a node on the cluster

- `vagrant ssh box02 -- sudo k3s agent --server https://192.168.56.1:6443 --flannel-iface eth1 --token ${NODE_TOKEN}`  add a node on the cluster

> `NODE_TOKEN` comes from `/var/lib/rancher/k3s/server/node-token` on your server

- `sudo mkdir /home/formation/.kube && sudo cp /etc/rancher/k3s/k3s.yaml /home/formation/.kube/config  && sudo chown formation:formation /home/formation/.kube/config`

- `wget https://dl.k8s.io/release/v1.27.2/bin/linux/amd64/kubectl && chmod +x kubectl && sudo mv kubectl /usr/local/bin/`

- `kubectl get node,svc,pod -A`

Autocompletion (https://gist.github.com/GusAntoniassi/2f58e716b67f648d13f91c1d780b05bf) : 

# kubectl with ZSH (oh-my-zsh)

## How to configure

Use the following commands to add the kubectl autocomplete to zsh:

```shell
mkdir -p ~/.oh-my-zsh/custom/plugins/kubectl-autocomplete/
kubectl completion zsh > ~/.oh-my-zsh/custom/plugins/kubectl-autocomplete/kubectl-autocomplete.plugin.zsh
```

After that, edit your `~/.zshrc` to include the plugin `kubectl-autocomplete`, like so:

```
# ~/.zshrc
# ...
plugins=(kubectl-autocomplete)
```

