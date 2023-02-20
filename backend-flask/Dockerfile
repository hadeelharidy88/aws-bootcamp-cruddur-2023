FROM python:3.10-slim-buster

#inside the container
WORKDIR /backend-flask

#outside --> inside
#this contains the libraries we want to install
COPY requirements.txt requirements.txt

#inside the container
#install python libraries used for the app
RUN pip3 install -r requirements.txt


#outside --> inside
# . everything in the current directory
# first period . - /backend-flask (outside container)
# second period . - /backend-flask (inside container)
COPY . .

#set env vars
#inside the container and remain set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

# command to run flask
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]
# python3 -m flask run --host=0.0.0.0 --port=4567