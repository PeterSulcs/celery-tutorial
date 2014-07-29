celery-tutorial
===============

Code to replicate celery tutorial: https://www.youtube.com/watch?v=68QWZU_gCDA&feature=youtu.be

setup
-----

Install ERLANG

Install RabbitMQ

(I think if you do this in order and you don't use a 32bit version of RabbitMQ and 64bit version of Erlang you can skip the ERLANG_HOME setup)

setup %ERLANG_HOME%

setup %RABBITMQ_SERVER%

add %RABBITMQ_SERVER%\sbin to PATH

```dos
rabbitmq-server
```

starts the server.

now run:

```dos
celery worker -A tasks -l INFO
```

now run:

```dos
ipython
```

```python
from tasks import add
for i in xrange(10000):
  add.delay(i, i)
```