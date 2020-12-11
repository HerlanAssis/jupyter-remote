#Sistema Operacional
FROM ubuntu:20.04

#Dependências do sistema
RUN apt-get update -y
RUN apt-get install -y python3-dev python3-pip build-essential
#Pacotes do Python
COPY requirements.txt /requirements.txt 
RUN pip3 install --upgrade pip
RUN pip3 install -r requirements.txt
RUN pip3 install jupyter
RUN pip3 install jupyter_http_over_ws
RUN jupyter serverextension enable --py jupyter_http_over_ws
RUN pip3 install --upgrade --force-reinstall --no-cache-dir jupyter

#Diretório do usuário docker
RUN mkdir -p /home/user
WORKDIR /home/user

COPY kaggle.json .