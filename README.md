celery-tutorial
===============

Code to replicate the celery tutorial linked below while running in a Windows 8.1 environment.

<a href="http://www.youtube.com/watch?feature=player_embedded&v=68QWZU_gCDA
" target="_blank"><img src="http://img.youtube.com/vi/68QWZU_gCDA/hqdefault.jpg" 
alt="Python Celery demo" width="240" height="180" border="10" /></a>

setup
-----

1. Install ERLANG from [here](http://www.erlang.org/download.html)
2. Install RabbitMQ from [here](https://www.rabbitmq.com/download.html)
   * I think if you do this in order and you don't use a 32bit version of RabbitMQ and 64bit version of Erlang you can skip the ERLANG_HOME setup
3. setup %ERLANG_HOME%
4. setup %RABBITMQ_SERVER%
5. add %RABBITMQ_SERVER%\sbin to PATH


6. Open a command window and type the following to start the server.
  ```dos
  rabbitmq-server
  ```
   * If you get a node already started error, open task manager and kill the Erlang interpreter if it is running.

7. In a second command window, run:

  ```dos
  celery worker -A tasks -l INFO
  ```

8. In a third command window, run:

  ```dos
  ipython
  ```
  
  ```python
  from tasks import add
  for i in xrange(10000):
    add.delay(i, i)
  ```
