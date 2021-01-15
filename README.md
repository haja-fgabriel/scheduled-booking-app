The main idea of this client-server application is to book tickets to given spectacles which occur in given theaters. The client has a set interval for sending place booking requests to the server, where all the given places are checked for being available.

It is built as a proof of concept for working with ExecutorService thread pools, Callables and Runnables, alongide with task scheduling using the Java built-in Timer and TimerTask classes.

The server is written using Spring Boot framework.
The client is written in Node, using the external XMLHttpRequest module, since node doesn't provide one.

Learnt lessons:
- Timer is an old, but fun to use class, which provides JavaScript-like features to Java (setting intervals for tasks and delayed execution);
- ExecutorService.submit does indeed return a future for the caller-provided task and return values, and not one for any submitted task.
- JavaScript promises are no longer a problem for me;
- I've used the Builder pattern to create Task instances, since Spring doesn't autowire any instance to the manually instantiated objects;
- don't forget to annotate all the important instances (e.g.: data entities, repositories and services), or Spring will get on your nerves

Further improvements:
- use a ScheduledExecutorService for submitting on interval instead of instantiating a Timer object which itself instantiates a TimerTask;
- randomly generate places on the client side;
- describe the controllers' API in this file.
