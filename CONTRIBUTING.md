#CONTRIBUTING   

## How to run docker file locally

````
 docker run -dp 5000:5000 -w /app -v "$(pwd):/app" IMAGE NAME sh -c "flask run --host 0.0.0.0"
````

## Docker file configuration

````
FROM python:3.10
EXPOSE 5000
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
RUN pip install flask
COPY . .
CMD ["flask", "run", "--host", "0.0.0.0"]
````