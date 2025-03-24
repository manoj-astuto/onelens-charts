#### Once the file is copied to repo onelens-charts - recreate the index.yaml 
helm repo index . --url https://manoj-astuto.github.io/onelens-charts

#### Push the latest changes tgz file and index.yaml to github 
git add .
git commit -m "new release published"
git push 

### Steps on the client cluster to execute
helm repo add onelens https://manoj-astuto.github.io/onelens-charts

helm repo update

helm upgrade --install onelensdeployer onelens/onelensdeployer --set job.env.TENANT_NAME=fresh --set job.env.CLUSTER_NAME=main


