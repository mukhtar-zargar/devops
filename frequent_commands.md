Dapr Run

'''
dapr run --app-id {test_app} --app-port 3000 --dapr-http-port 3500 npm start
'''

Node - install eslint prettier nodemon tsc

'''
npm install -D @types/node eslint eslint-config-prettier eslint-plugin-prettier nodemon prettier ts-node typescript
'''

Powershell - Invoke-RestMethod [curl alt]

'''
Invoke-RestMethod -Method Get -Headers @{'dapr-app-id' = 'ghost_app'} -Uri 'http://localhost:3500/grapgql'
'''

Pwrshell - Dapr install
'''
powershell -Command "iwr -useb https://raw.githubusercontent.com/dapr/cli/master/install/install.ps1 | iex"
'''

Docker run
'''
docker run -p 3000:3000 -d --name ghost --env-file .env ghost:0.1  
'''

Docker build
'''
docker build . -t ghost:0.1  
'''

Docker compose up:

'''
docker compose -f .\dockercompose-ghost.yaml up -d
'''
