# helm-hook-demo
-- Steps :
* git clone https://github.com/sanjaytiwari007/helm-hook-demo.git
* cd helm-hook-demo
* helm install --wait --wait-for-jobs hookjob --debug .
- To Delete
* Create a secret seperatly
* kubectl create secret generic hookdemo-test-secret --from-literal=username=sanjay --from-literal=password=tiwari
* helm uninstall hookdemo .
