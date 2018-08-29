## INSTALLATION


### Using docker-compose (Recommended) 
* Download and Install Docker Community Edition
* Navigate to Project Directory  

```sh
#Build the images
docker-compose build

#Fire up  the containers
docker-compose up -d

#Check if there are 3 containers running(backend, frontend & mongodb)
docker ps

#Initialize Data
docker-compose exec backend python manage.py init

#http://localhost:8080
```


### Without Docker

#### Backend

* Setup Virtualenv and install python requirements

```sh
make setup

make run_dev

source venv/bin/activate && python manage.py init
```
* Production

```sh
make run_prod
```

#### Frontend

* Development

```sh
cd frontend
npm install
ng serve
```

* Production

```sh
cd frontend
ng build --prod --environment=python
```
serve files in dist/ folder using nginx or any webserver

### Deploy To Heroku
[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)

* add your dev/production configurations in config.py


#### Restore / Load Customized Intent / Training File
You can import some default intents using follwing steps

- goto http://localhost:8080/agent/default/settings
- click 'choose file'
- choose 'examples/default_intents.json file'
- click import

