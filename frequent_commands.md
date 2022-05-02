# Frequently Used Commands

- Dapr Run

`dapr run --app-id {test_app} --app-port 3000 --dapr-http-port 3500 npm start`

- Node - install eslint prettier nodemon tsc

`npm install -D @types/node eslint eslint-config-prettier eslint-plugin-prettier nodemon prettier ts-node typescript`

- Powershell - Invoke-RestMethod [curl alt]

`Invoke-RestMethod -Method Get -Headers @{'dapr-app-id' = 'ghost_app'} -Uri 'http://localhost:3500/grapgql'`

- Pwrshell - Dapr install
  `powershell -Command "iwr -useb https://raw.githubusercontent.com/dapr/cli/master/install/install.ps1 | iex"`

- Docker run
  `docker run -p 3000:3000 -d --name ghost --env-file .env ghost:0.1 `

- Docker build
  `docker build . -t ghost:0.1 `

- Docker compose up:

`docker compose -f .\dockercompose-ghost.yaml up -d`

- K8 admin dashboard
  `kubectl apply -f https://raw.githubusercontent.com/kubernetes/dashboard/v2.5.0/aio/deploy/recommended.yaml`

- Admin Url: http://localhost:8001/api/v1/namespaces/kubernetes-dashboard/services/https:kubernetes-dashboard:/proxy/

- Apply yaml file

`kubectl apply -f .\dashboard-adminuser.yaml`

- Get bearer token
  `kubectl -n kubernetes-dashboard get secret $(kubectl -n kubernetes-dashboard get sa/admin-user -o jsonpath="{.secrets[0].name}") -o go-template="{{.data.token | base64decode}}"`

- Get Pod Details
  `kubectl get pods,svc --all-namespaces -o wide`

- MONGODB docker envs
  `MONGO_INITDB_ROOT_USERNAME MONGO_INITDB_ROOT_PASSWORD`

- k8 create secrets from .env file
  `kubectl create secret generic ghost-secrets --from-env=.env`

- k8 edit secrets file
  `kubectl edit secrets ghost-secrets`

- k8 logs
  `kubectl logs ghost-96bfd4497-696sd`
