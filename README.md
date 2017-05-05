# pintdocker
This is a small Docker tutorial. As a use-case the tutorial setups a python-django container.

The target of this tutorial is to create a python-django container. After you clone this repository you will have a directory with 
the following set of files

* Dockerfile

```bash
FROM python:2
 ENV PYTHONUNBUFFERED 1
 RUN mkdir /code
 WORKDIR /code
 ADD requirements.txt /code/
 RUN pip install -r requirements.txt
 ADD . /code/
```

* docker-compose.yml

```bash
 version: '2'
 services:
   web:
     build: .
     command: python2 manage.py runserver 127.0.0.1:8000
     volumes:
       - .:/code
     ports:
       - "8000:8000"
 ```
 * requirements.txt
 
```bash
Django>=1.8,<2.0
```

 

  

