# INFO8995-observability
run kubernetes dashboard in codespace

TLDR;

```
pip install -r requirements.txt
ansible-playbook playbook.yml
kubectl get pods
```
Then with the 0th pod, dashboard-kong-68687498db-5jk5m in my case run:

```
kubectl -n default port-forward dashboard-kong-68687498db-5jk5m 8443:8443
```

You will need a bearer token to access the dashboard. Open a 2nd terminal window and run:

```
kubectl -n default create token admin-user
```

If you need to delete a cluster and start over you can run:

```
k3d cluster delete local-k8s
rm -rf ~/.kube
```

Then you can take it from the top.

Note: This also works (faster) in vscode local with docker desktop installed. 

1. From the command palette `Dev Containers: Clone Repository in Container Volume`. 

2. Choose this repository `https://github.com/rhildred/INFO8985-observability.git`. 

3. Follow the steps from TLDR;

The deliverable for the lab is to create a deployment diagram using [https://www.umletino.com/umletino.html](https://www.umletino.com/umletino.html). This can be done by dragging and dropping pods you see with the `kubectl get pods` command. A starting place would be something like this:

![deployment diagram](READMEImages/deployment.png)

Hopefully this is a gentle introduction to ansible and kubernetes.
