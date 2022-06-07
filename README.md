# signalrchatyaml          
OCP DevOps Demo

#Prerequisites:
1. Install Required Operators
     - CodeReady Workspaces
     - OpenShift Pipelines
     - Openshift Cluster Logging
     - Openshift Elastic 
2. Create CodeReady Workspace cluster
     oc apply -f prerequisites/codeready.yaml
3. Create cluster logging instance
4. Deploy Sonarqube
     oc apply -f prerequisites/sonarqube.yaml
5. Configure sonarqube
     - add signalrchat project
6. Create Pipeline
     oc apply -f pipeline/namespace.yaml
     oc apply -f pipeline/rbac.yaml
     oc apply -f pipeline/task.yaml
     oc apply -f pipeline/signal-build-and-deploy.yaml
     oc apply -f pipeline/signal-deploy-to-uat.yaml
     oc apply -f pipeline/signal-deploy-to-prod.yaml
7. Update github token in deploy-to-uat and deploy-to-production pipeline
     - Create github Personal Access token
     - Update git url parameter in signal-deploy-to-uat & signal-deploy-to-prod parameter 
8. Update sonarqube url in build and deploy to dev pipeline
9. Login and configure Kibana
     - Create index pattern & log view (show container name & messages)
10. Configure Github Webhook
