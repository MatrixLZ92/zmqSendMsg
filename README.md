# zmqSendMsg
Refer to http://osdevlab.blogspot.com/2015/12/how-to-send-message-between-c-and.html


# How to build
```
> cd{r, attr.source='.numberLines startFrom="5"'} zmqSendMsg
> mkdir -p build && cd build
> cmake ..
> make
```

# Revise Note
Error
```
Traceback (most recent call last):
  File "client.py", line 9, in <module>
    socket.send("saying hello from python")
  File "/home/username/.local/lib/python3.8/site-packages/zmq/sugar/socket.py", line 618, in send
    return super().send(data, flags=flags, copy=copy, track=track)
  File "zmq/backend/cython/socket.pyx", line 740, in zmq.backend.cython.socket.Socket.send
  File "zmq/backend/cython/socket.pyx", line 784, in zmq.backend.cython.socket.Socket.send
TypeError: unicode not allowed, use send_string
```
Change the following code in client.py
```
socket.send("saying hello from python")
```
to
```
socket.send_string("saying hello from python")
```
