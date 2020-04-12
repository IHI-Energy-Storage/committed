FROM continuumio/miniconda3

# Install necessary packages
RUN apt-get -y install vim
RUN apt-get -y install jq
RUN apt-get -y install curl
RUN apt-get -y install unzip
RUN pip install cerberus
RUN pip install behave-py3
RUN pip install coverage
RUN pip install Pandas3
RUN pip install PyYAML
RUN pip install pydriller
RUN ln -s /opt/conda/bin/python3 /usr/local/bin/python3
RUN /opt/conda/bin/conda install jupyter -y --quiet

RUN mkdir /etc/committed

COPY ./committed/ /etc/committed/

ENTRYPOINT /opt/conda/bin/jupyter notebook --notebook-dir=/etc/committed/notebooks/ --ip='*' --port=8888 --no-browser --allow-root
