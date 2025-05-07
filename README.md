# Some troubleshooting Scenarios for openshift lightspeed testing / demo



## Deploying
You can use the argo app to better manage the test (reset).

Of course, since things are broken on purpose, argocd won't give you a green tic after deploying the resources. That's expected.


## Warnings
test-06 has on purpose some finalizer hanging around. This means that if you legitimeltly want to remove the namespace from your cluster, well, you will have to remove the finalizers. Argocd won't do it for you.

## solution to the exercise

https://trbl-workshop.cszevaco.com/workshop

## Exercise 4 youtube demo:

https://youtu.be/nR9sLKmgPdI

## blog post

https://blog.cszevaco.com/blog/lightspeed-benchmark
