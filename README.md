# Python_Server_Client
python server, client for sending and receiving message / file

multi acceptable server

multi instanceable, simultaneous downloadable, simultaneous upload available client

client :

d-> download

u-> upload

q-> terminate server

b-> disconnect client

![001](https://user-images.githubusercontent.com/72921481/146724382-41f8f6a6-d2c2-4db6-b3ca-6309603ee44c.png)
![003](https://user-images.githubusercontent.com/72921481/146724397-dcfe7077-5b17-43bf-812a-d6f72243198f.png)

Running the server, whenever a new client connects, a thread is created to communicate with it.


The spawned thread always waits to receive a message from the client.


A thread is also created when sending a message. Accordingly, it is possible to send multiple data to and from one client at the same time, and communicate with multiple clients at the same time.



When sending/receiving internal messages or files from server/client, system messages are delivered, and data parsing is used to increase stability and speed.


The thread created for reception is designed so that the user can execute the desired function whenever a message is received.



![002](https://user-images.githubusercontent.com/72921481/146724391-236d5fe0-27bf-472e-bfa4-8793387cbeb1.png)
![004](https://user-images.githubusercontent.com/72921481/146724398-ea134c19-a390-4527-b04f-0fb8ac2a017b.png)


When a client instantiates, it registers an ID.


The client's Receiver is executed through a thread. Like the server, it receives messages at every moment, and can be parsed between messages and commands with \0 and ",".


Like the server, the client can transmit/receive at the same time and can create multiple instances.


Download and Upload are performed by creating instances of Downloader and Uploader classes that inherit from Client.


One client/server communicates serially.


Since it creates and communicates with Downloader and Uploader instances, two or more downloads and uploads can be performed at the same time.


Each class user-specified function exists and is executed when receiving, downloading, and uploading a message.
