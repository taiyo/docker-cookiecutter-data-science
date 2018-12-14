FROM jupyter/datascience-notebook
LABEL  maintainer taiykato

USER root

RUN apt-get update && apt-get install -y \
  fonts-takao

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt
# If notebook version under 5.3, required
# RUN jupyter serverextension enable --py jupyterlab
