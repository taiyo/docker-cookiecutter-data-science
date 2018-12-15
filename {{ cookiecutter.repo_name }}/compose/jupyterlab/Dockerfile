FROM jupyter/datascience-notebook
LABEL  maintainer taiykato

USER root

RUN apt-get update

COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt
# If notebook version under 5.3, required
# RUN jupyter serverextension enable --py jupyterlab

# matplotlibで日本語が表示されるようにフォントを設定
RUN curl -L  "https://oscdl.ipa.go.jp/IPAexfont/ipaexg00301.zip" > font.zip
RUN unzip font.zip
RUN cp ipaexg00301/ipaexg.ttf /opt/conda/lib/python3.6/site-packages/matplotlib/mpl-data/fonts/ttf/ipaexg.ttf
RUN echo "font.family : IPAexGothic" >>  /opt/conda/lib/python3.6/site-packages/matplotlib/mpl-data/matplotlibrc
RUN rm -r ./.cache
