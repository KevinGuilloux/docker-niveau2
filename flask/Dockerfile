FROM harbor.localhost/cache/python:3.12.0b4-slim

WORKDIR /python-docker

RUN apt-get update && apt-get -y install procps curl

RUN groupadd -g 1500 nonroot && \
    useradd -u 1500 nonroot -g 1500 -m

# RUN mkdir /.local && \
#     chown nonroot:nonroot /.local

USER nonroot:nonroot

COPY requirements.txt requirements.txt
RUN pip3 install -r requirements.txt

COPY app.py .

EXPOSE 8080

HEALTHCHECK --interval=1m --timeout=5s --retries=3 CMD curl --fail http://localhost:5000 || exit 1

CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0"]
