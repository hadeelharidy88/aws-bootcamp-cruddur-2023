# Week 1 — App Containerization

## Docker for VS Code was installed:

![image](https://user-images.githubusercontent.com/91920047/227708754-212d5f46-d2b8-4141-b5cb-720bc979a1d1.png)

## Containerized the backend:

1) Add Dockerfile:

![image](https://user-images.githubusercontent.com/91920047/227708807-bf2a3e41-66b5-4c58-b4d6-14c98ea93e8f.png)

2) Build Container:

```
docker build -t  backend-flask ./backend-flask
```

3) Run Container:

```
docker run --rm -p 4567:4567 -it -e FRONTEND_URL='*' -e BACKEND_URL='*' backend-flask
```
4) Open port to public and test it by adding //api/activities/home to URL.

![image](https://user-images.githubusercontent.com/91920047/227708976-5c54508b-ab7d-486f-9e9c-419f4ac2e3e3.png)

## Containerized the frontend:

1) First run NPM Install:

```
cd frontend-react-js
npm i
```

2) Add Dockerfile:

![image](https://user-images.githubusercontent.com/91920047/227709003-06a59a71-eeb8-4040-9730-af02c289eee3.png)

3) Build Container:

```
docker build -t frontend-react-js ./frontend-react-js
```
4) Run Container:

```
docker run -p 3000:3000 -it  -e FRONTEND_URL='*' -e BACKEND_URL='*' frontend-react-js
```

## Run Multiple Containers

1) Create a docker-compose file

![image](https://user-images.githubusercontent.com/91920047/227709239-73b7dc2a-0141-4f9e-a8c9-16e31582b396.png)

2) Compose up to run both backend and frontend services other then open both ports.

### Backend:

[[https://4567-hadeelharid-awsbootcamp-rtowlqj20j9.ws-eu92.gitpod.io/api/activities/home]]

![image](https://user-images.githubusercontent.com/91920047/227709322-03b2a112-8a99-4238-b09f-20bdf9d25c3d.png)


### Frontend:

[[https://3000-hadeelharid-awsbootcamp-rtowlqj20j9.ws-eu92.gitpod.io/]]

![image](https://user-images.githubusercontent.com/91920047/227709495-ee1b36af-2cf9-4491-b1b0-b982a2948bf6.png)


## Adding DynamoDB Local and Postgres

### First install the postgres client and PostreSQL extention into Gitpod.

![image](https://user-images.githubusercontent.com/91920047/227709726-7acde6c3-a5cb-4a44-94e9-3c8f96308a4a.png)

Add both services to docker-compose file as below:

![image](https://user-images.githubusercontent.com/91920047/227709608-cece0952-92e0-41ab-8171-cd67845d4319.png)

Test Connection to PostgreSQL server.

![image](https://user-images.githubusercontent.com/91920047/227709782-e8063df2-2f70-4c40-b85f-0bbeb8f01efa.png)

