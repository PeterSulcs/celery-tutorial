celery-tutorial
===============

Code to replicate celery tutorial.

setup
-----

Install ERLANG

Install RabbitMQ

(I think if you do this in order and you don't use a 32bit version of RabbitMQ and 64bit version of Erlang you can skip the ERLANG_HOME setup)

setup %ERLANG_HOME%

setup %RABBITMQ_SERVER%

add %RABBITMQ_SERVER%\sbin to PATH

>rabbitmq-server

starts the server.

now run:

>>celery worker -A tasks -l INFO

now run:

>>ipython

```python
from tasks import add
for i in xrange(10000):
  add.delay(i, i)
```
