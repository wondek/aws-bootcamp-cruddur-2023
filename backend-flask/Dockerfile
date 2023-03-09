FROM python:3.10-slim-buster

#inside Container
#make a new folder inside container 
WORKDIR /backend-flask

#Outside Container -> Inside Container
#this containes the libraries we want to install to run the App
COPY requirements.txt requirements.txt

#Inside Container 
#will install the python libraries used for the App
RUN pip3 install -r requirements.txt

#Outside Container -> Inside Container 
# . means everything in the current directory 
# first period  . -/backend-flask ( outside container )
# second period  . -/backend-flask ( inside container )
COPY . .

# Set environment variabls (Env Vars) 
#Inside Container and will remain set when the container is running
ENV FLASK_ENV=development

EXPOSE ${PORT}

#CMD (Command)
# The command to run Flask 
# python3 -m flask run --host=0.0.0.0 --port=4567
CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]