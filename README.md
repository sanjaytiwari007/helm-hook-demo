# helm-hook-demo
### __Steps__ :
* Clone the repo
  * `git clone https://github.com/sanjaytiwari007/helm-hook-demo.git`
* go to the repo directory:  `cd helm-hook-demo`

#### _Install helm chart_
  * `helm install --wait --wait-for-jobs hookjob --debug .`
  * With above command helm will wait for all the jobs to be finised before running helm post-intall hook
  * Test the job by running kubectl command
   * `kubectl get jobs`
  * Test the secret created by job which will be deleted by post-delete hook
   * `kubectl get secret`

#### _Delete Helm Chart_
* Run following command to uninstall helm charts
  * `helm uninstall hookjob .`
* Helm uninstall will trigger delete hook and will delete the secret created by install job.
* Validate the secreate is gone by running
  * `kubectl get secret`

__NOTE__ : We have sleep in job in order to validate pods log for all the commands in job.
