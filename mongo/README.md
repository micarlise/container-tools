## build container

**prereq:** build base container first

```
docker build -t tools-mongo .
```

## Connect to an internal mongo service

*Docker*

```
docker run -it --name mongo-cli tools-mongo <connection_uri>
```

**May need to specify --net**
