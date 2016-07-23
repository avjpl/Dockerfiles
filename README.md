Rabbitmq

Build with:

```
docker build -t rabbitmq .
```

Run with:

```
docker run -d -p 5672:5672 -p 15672:15672 -p 25672:25672 -p 1883:1883 -p 61613:61613 --name rabbitmq rabbitmq
```

MongoDB

Build with:

```
docker build -t mongodb .
```

Run with:

```
docker run --name mongodb -d -p 27017:27017 mongo
```
