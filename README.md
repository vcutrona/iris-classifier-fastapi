# Serving Iris Classifier with FastAPI

## Data

The Iris dataset is a simple, yet popular dataset consisting of 150 observations. Each observation captures the sepal length, sepal width, petal length, petal width of an iris (all in cm) and the corresponding iris subclass (one of *setosa, versicolor, virginica*).

![](https://s3.amazonaws.com/assets.datacamp.com/blog_assets/Machine+Learning+R/iris-machinelearning.png)


## Usage

Make sure you have Docker installed.

1. Build the docker image using `docker build . -t iris`
2. Run the docker container using `docker run -i -d -p 8080:5000 iris`

The input is a JSON with the following fields:

* sepal_length
* sepal_width
* petal_length
* petal_width

Corresponding values are the measurements in cm.

Example request:

```shell
curl 'http://localhost:8080/iris/classify_iris' -X POST -H 'Content-Type: application/json' -d '{"sepal_length": 5, "sepal_width": 2, "petal_length": 3, "petal_width": 4}'
```
