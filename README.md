[![Beekan](https://circleci.com/gh/Beekan/ml_microservices_kubernetes.svg?style=svg)](https://app.circleci.com/pipelines/github/Beekan/ml_microservices_kubernetes?branch=main)


## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API.

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Tasks

Your project goal is to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project you will:

* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

You can find a detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The final implementation of the project will showcase your abilities to operationalize production microservices.**

---

## Setup the Environment

* Create a virtualenv and activate it
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl

## Summary

This project is a simple prediction estimator using sklearn to predict housing prices. The project is containarized using docker and orchestrated using kubernetes. The application is implemented using flask to respond to post requests.

## How to use

To first spin up the cluster:
```
./run_kubernetes.sh
```

The backend is now listining on port 8000

To make a prediction:
```
./make_prediction.sh
```

## Short description of files

.circleci/config.yml: The Continious integration file which runs on each commit.

app.py: Contains the flask application which takes in the prediction post requests.

Dockerfile: A yaml file containing the configuration of the container used to run the model.

Makefile: Contains some presets the are reusable which can be run repeatedly with ease.

requirements.txt: contains the required libraries for the app.py to run

run_docker.sh: A bash script that spins up the docker container an exposes the port to the host.

run_kuberenets: A bash script that spins up a pod called app containing the container from the docker repository.

upload_docker: A bash script which uploads the local built image to the docker repository.
