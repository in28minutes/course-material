FROM python:alpine3.10
WORKDIR /app 
COPY . /app
RUN pip install -r requirements.txt
EXPOSE 8080
CMD python ./launch.py

#COPY requirements.txt /app/requirements.txt
#ENTRYPOINT ["python", "./launch.py"]
