# Some Scenarios for openshift lightspeed testing

## Deploying
You can use the argo app to better manage the test (reset).

## Warnings
test-06 has on purpose some finalizer hanging around. This means that if you legitimeltly want to remove the namespace from your cluster, well, you will have to remove the finalizers. Argocd won't do it for you.
