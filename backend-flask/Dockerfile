FROM python:3.10-slim-buster
# DockerHub OS and tag --> OS release
# Inside Container --> OS Kernel, make a new folder
WORKDIR /backend-flask

#Outside -> Inside
#this contains the libraries we want to install to run the app
COPY requirements.txt requirements.txt

#Inside Container
#install th python libraries used for the app
RUN pip3 install -r requirements.txt

# Outside Container -> Inside Container
# . means everything in the current directory
# first period . /backend-flask (outside container)
# second period. /backend-flask (inside container)
COPY . .

#Set Environment Variables (Env Vars)
# Inside Container and will remain set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

# rinning command--> python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]
