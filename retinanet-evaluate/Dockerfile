FROM tensorflow/tensorflow:latest-gpu-py3
RUN apt-get clean && \
    apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y git
RUN git clone https://github.com/fizyr/keras-retinanet
RUN cd keras-retinanet && pip install . --user
RUN pip install opencv-python
RUN apt-get install -y libsm6 libxrender1
ENTRYPOINT ["/bin/bash", "-c", "/root/.local/bin/retinanet-evaluate ${*}", "--"]
