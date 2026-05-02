# Base image
FROM ubuntu:latest

# Paketləri yeniləyirik
RUN apt-get update && apt-get upgrade -y

# Python və pip yükləyirik
RUN apt-get install -y python3 python3-pip

# Mümkün xətanın qarşısını almaq üçün (tapşırıqda qeyd edilib)
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED || true

# Flask yükləyirik
RUN pip3 install flask

# İş qovluğunu /app edirik
WORKDIR /app

# Bayaq yaratdığımız api.py faylını Docker-in içinə kopyalayırıq
COPY ./api.py /app/api.py

# Konteyner işə düşəndə serveri aktivləşdiririk
CMD ["python3", "api.py"]