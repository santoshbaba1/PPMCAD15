The meaning of running multiple containers within a pod is as follows:

how do you run containers within a pod..

- suppose you have a micro-service based application with 5 microservices running in it.
    - ui
    - api
    - login
    - backend
    - notification

all 5 are nodejs based apps.. and they have to deploy them into K8S

- no 2 MS/App should be deployed within 1 pod

- each of the 5 MS will be deployed into separate pods

- Replicas - Running multiple pods for a single MS/app

- then why do we need multiple containers within a single pod?
    - If I need 2 containers with the api pods, what would be the role of the 2nd container?
    - sidecar container / supporting container to the main container
        - log shipper container - this is the container which will run alongside my main api container 
            - it will have access to the same disk of my api container
            - and it will continuously monitor the logs and make sure to ship it to an external source
        - health check container