#Download base image ubuntu
FROM ubuntu:latest

MAINTAINER Tan-mba Takougnadi

WORKDIR /workspace

COPY . /workspace 

RUN apt-get update -y && apt-get dist-upgrade -y 

RUN apt-get install python3 -y 

RUN apt-get install python3-pip -y  

RUN pip3 install virtualenv 

RUN apt-get install git -y 

RUN git config --global user.name "John Doe" && \
    git config --global user.email johndoe@example.com && \
    git config --global user.password "password"

RUN virtualenv -p python3 venv 

CMD sh -c 'source venv/bin/activate;'

RUN pip freeze > requirements.txt

EXPOSE 8888

CMD ["sh", "-c" , "jupyter notebook --no-browser --port=8888 --ip='0.0.0.0'
--allow-root"]
