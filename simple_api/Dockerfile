FROM python:2.7-stretch
LABEL maintainer="Francis ABODO abodojustin@gmail.com"
COPY student_age.py /
#Update stretch repositories
RUN sed -i s/deb.debian.org/archive.debian.org/g /etc/apt/sources.list; \
    sed -i 's|security.debian.org|archive.debian.org/|g' /etc/apt/sources.list; \
    sed -i '/stretch-updates/d' /etc/apt/sources.list; \
    apt-get update -y && apt-get install python-dev python3-dev libsasl2-dev python-dev libldap2-dev libssl-dev -y; \
    pip install flask==1.1.2 flask_httpauth==4.1.0 flask_simpleldap python-dotenv==0.14.0; \
    mkdir /data
COPY ./student_age.json /data
#EXPOSE 5000
CMD ["python", "./student_age.py"]