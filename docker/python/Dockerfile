FROM python

RUN mkdir /python_app

WORKDIR /python_app

COPY src /python_app

RUN pip install -r requirements.txt

EXPOSE 8083
CMD ["python","server.py"]