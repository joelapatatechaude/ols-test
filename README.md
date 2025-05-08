# Some troubleshooting Scenarios for openshift lightspeed testing / demo


## Deploying with ArgoCD
You can use the argo app to better manage the test (reset the changes when needed).
something like this should work:
```bash
cd ols-test/argocd-app
oc apply -f .
```

Of course, since each of the namespaces are broken on purpose, argocd won't give you a green tic after deploying the resources. That's expected.

## Deploying directly
Something like this should work, for each test:
```bash
cd ols-test/lightspeed-benchmark/test-01
oc apply -f .
```
**test-06** has a sub directory, the recursive flag is needed:
```bash
cd ols-test/lightspeed-benchmark/test-06
oc apply -f . --recursive
```

## Warnings
test-06 on purpose has some finalizer hanging around. This means that if you legitimeltly want to remove the namespace from your cluster, well, you will have to remove the finalizers. Argocd won't do it for you. If you need help, well, ask LightSpeed!! Or read the solution -> https://trbl-workshop.cszevaco.com/workshop/exercise_06#solution

## Solution to the tests

https://trbl-workshop.cszevaco.com/workshop

## Exercise 4 youtube demo:

https://youtu.be/nR9sLKmgPdI

## Blog post
This blog post is using the 6 tests as a benchmark to test a few LLM model used with LightSpeed: granite-3.2-8b-instruct, granite-3.2-2b-instruct, and openai gpt-4o-mini
https://blog.cszevaco.com/blog/lightspeed-benchmark
