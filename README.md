# CET
Communications Event Timer

Runs an event programming function or object method at a scheduled time with cron or windows event scheduler.

This is an implementation of CET with an ephemeris and SMS

https://www.fullstackpython.com/blog/send-sms-text-messages-python.html
http://www.ascl.net/1112.014

Temporal Logic & Event Management

This paradigm attempts to include time based logical control over a programming code sequence that would be typically considered as part of the operating system, with cron in unix for example.  However, I am including this concept in a book on programming to establish this paradigm as an essential conceptual feature in programming in a universal sense.

import time

def func(arg):
    print arg

a = time.time()+100
while 1:
    If time.time()<a:
        time.sleep(30)
    else:
        func(‘hello world!’)
        break

Another interesting variation is to perennially repeat this “timed” function call by adding 60 seconds to the timing feature every time the function is called:

import time

def func(arg):
    print arg

a = time.time()+100
while 1:
    If time.time()<a:
        time.sleep(30)
    else:
        func(‘hello world!’)
        a = a + 60
#break

Also, consider a list of functions each with a time key to be executed temporally:

import time

def func(arg):
    print arg

def func2():
    print ‘hello world2!’

def func3():
    Print ‘hello world3!’

a = time.time()+ 100
b = time.time() + 50
c = time.time() + 125

e = {a: func, b: func2, c: func3}

while 1:
    for x in e.keys()
    if time.time()<x:
            continue
        else:
            e[x]()
            e.pop(x, 0)
    if e:
    time.sleep(30)
    else:
        break
    
Also, using the same code, you can manipulate the event dictionary data structure to execute the listed function at timed intervals:

import time

def func(arg):
    print arg

def func2():
    print ‘hello world2!’

def func3():
    Print ‘hello world3!’

a = time.time()+ 100
b = time.time() + 50
c = time.time() + 125

e = {a: [func, 45], b: [func2, 60], c: [func3, 20]}

while 1:
    for x in e.keys()
    if time.time()<x:
            continue
        else:
            e[x]()
            e[x+e[x][1]] = [e[x][0], e[x][1]]
            e.pop(x, 0)
time.sleep(30)
