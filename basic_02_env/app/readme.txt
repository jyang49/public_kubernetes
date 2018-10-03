# this version of app uses environment variable

docker build -t myapp-env .

docker tag myapp-env jyang4900/myapp-env

docker push jyang4900/myapp-env

# pass env when running with docker

docker run -p 8080:8080 -e "hobby=study" myapp-env
