FROM python:2.7-alpine

#copy the requirements files into the image
COPY ./requirements.txt /app/requirements.txt

#switching working directory 
WORKDIR /app

#upgrade pip to the latest version
RUN pip install --upgrade pip

#install the dependencies and packages in the requirements file
RUN pip install -r requirements.txt

#copy every content from the local file to the image
COPY . /app

#expose on port 80
EXPOSE 80

CMD ["gunicorn"  , "-b", "0.0.0.0:80", "app:app"]