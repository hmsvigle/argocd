# argocd
Argocd files to refer from argocd_helm repo
# Notes
1. Steps to deploy `hello-world` app to `stg` & `reg` namespace:
   * Create application yaml for individual environments.
   * make sure to have diff application object name for the app for every env, as all the applications will be deployed in argocd namespace
  ````bash
  controlplane: k apply -f tibco/apps/hello-world/hello-world-stg-application.yaml -n argocd
   application.argoproj.io/helm-app-stg created
  ````
  * In case of Manual sync app has to be synced to reflect in respective destination namespace
  <img width="855" alt="argocd-app-sync" src="https://github.com/hmsvigle/argocd/assets/24938159/31aecdb9-e89c-40f1-bf0b-acbfc565de8c">

2. Application names in argocd has to be defined as `appName-<env>` as all applications will be deployed into argocd namespace
  * `Risk:`
    - argocd namespace has to be backed up frequently
    - Deleting application resource from argocd will delete the application from resepctive namespaces
2. Currently tested only 1 application directory containng all the 
3. Global emnvironment folder & templlate folder to be placed outside once, instead of repeating for all applications - `TO BE TESTED`
 
