### Introduction

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/5dede7b6-53ab-4927-81bc-6668b1c94677)

### Task 2 : The OSI Model : An Overview

The OSI (Open Systems Interconnection) Model is a standardised model which we use to demonstrate the theory behind computer networking. In practice, it's actually the more compact TCP/IP model that real-world networking is based off; however the OSI model, in many ways, is easier to get an initial understanding from.

The OSI model consists of seven layers:

Table showing the OSI layers: Application, Presentation, Session, Transport, Network, Data Link, Physical

There are many mnemonics floating around to help you learn the layers of the OSI model -- search around until you find one that you like.

I personally favour: Anxious Pale Shakespeare Treated Nervous Drunks Patiently

Let's briefly take a look at each of these in turn:

Layer 7 -- Application:

The application layer of the OSI model essentially provides networking options to programs running on a computer. It works almost exclusively with applications, providing an interface for them to use in order to transmit data. When data is given to the application layer, it is passed down into the presentation layer.

Layer 6 -- Presentation:

The presentation layer receives data from the application layer. This data tends to be in a format that the application understands, but it's not necessarily in a standardised format that could be understood by the application layer in the receiving computer. The presentation layer translates the data into a standardised format, as well as handling any encryption, compression or other transformations to the data. With this complete, the data is passed down to the session layer.

Layer 5 -- Session:

When the session layer receives the correctly formatted data from the presentation layer, it looks to see if it can set up a connection with the other computer across the network. If it can't then it sends back an error and the process goes no further. If a session can be established then it's the job of the session layer to maintain it, as well as co-operate with the session layer of the remote computer in order to synchronise communications. The session layer is particularly important as the session that it creates is unique to the communication in question. This is what allows you to make multiple requests to different endpoints simultaneously without all the data getting mixed up (think about opening two tabs in a web browser at the same time)! When the session layer has successfully logged a connection between the host and remote computer the data is passed down to Layer 4: the transport Layer.

Layer 4 -- Transport:

The transport layer is a very interesting layer that serves numerous important functions. Its first purpose is to choose the protocol over which the data is to be transmitted. The two most common protocols in the transport layer are TCP (Transmission Control Protocol) and UDP (User Datagram Protocol); with TCP the transmission is connection-based which means that a connection between the computers is established and maintained for the duration of the request. This allows for a reliable transmission, as the connection can be used to ensure that the packets all get to the right place. A TCP connection allows the two computers to remain in constant communication to ensure that the data is sent at an acceptable speed, and that any lost data is re-sent. With UDP, the opposite is true; packets of data are essentially thrown at the receiving computer -- if it can't keep up then that's its problem (this is why a video transmission over something like Skype can be pixelated if the connection is bad). What this means is that TCP would usually be chosen for situations where accuracy is favoured over speed (e.g. file transfer, or loading a webpage), and UDP would be used in situations where speed is more important (e.g. video streaming).

With a protocol selected, the transport layer then divides the transmission up into bite-sized pieces (over TCP these are called segments, over UDP they're called datagrams), which makes it easier to transmit the message successfully. 

Layer 3 -- Network:

The network layer is responsible for locating the destination of your request. For example, the Internet is a huge network; when you want to request information from a webpage, it's the network layer that takes the IP address for the page and figures out the best route to take. At this stage we're working with what is referred to as Logical addressing (i.e. IP addresses) which are still software controlled. Logical addresses are used to provide order to networks, categorising them and allowing us to properly sort them. Currently the most common form of logical addressing is the IPV4 format, which you'll likely already be familiar with (i.e 192.168.1.1 is a common address for a home router).

Layer 2 -- Data Link:

The data link layer focuses on the physical addressing of the transmission. It receives a packet from the network layer (that includes the IP address for the remote computer) and adds in the physical (MAC) address of the receiving endpoint. Inside every network enabled computer is a Network Interface Card (NIC) which comes with a unique MAC (Media Access Control) address to identify it.

MAC addresses are set by the manufacturer and literally burnt into the card; they can't be changed -- although they can be spoofed. When information is sent across a network, it's actually the physical address that is used to identify where exactly to send the information.


Additionally, it's also the job of the data link layer to present the data in a format suitable for transmission.

The data link layer also serves an important function when it receives data, as it checks the received information to make sure that it hasn't been corrupted during transmission, which could well happen when the data is transmitted by layer 1: the physical layer.

Layer 1 -- Physical:

The physical layer is right down to the hardware of the computer. This is where the electrical pulses that make up data transfer over a network are sent and received. It's the job of the physical layer to convert the binary data of the transmission into signals and transmit them across the network, as well as receiving incoming signals and converting them back into binary data.

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/e74bd06b-0647-4711-9b33-6d2b5712395a)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/12499491-c8b2-4059-886f-be673d80c455)

### Task 3 : Encapsulation

As the data is passed down each layer of the model, more information containing details specific to the layer in question is added on to the start of the transmission. As an example, the header added by the Network Layer would include things like the source and destination IP addresses, and the header added by the Transport Layer would include (amongst other things) information specific to the protocol being used. The data link layer also adds a piece on at the end of the transmission, which is used to verify that the data has not been corrupted on transmission; this also has the added bonus of increased security, as the data can't be intercepted and tampered with without breaking the trailer. This whole process is referred to as encapsulation; the process by which data can be sent from one computer to another.

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/3123ea2d-898d-4c7d-b8ec-3673066ccba8)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/ac58d58a-25b0-4554-95b0-16f7b934046e)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/287b876c-a38c-441f-9a1f-c1be053142d3)

### Task 4 : The TCP/Ip Model 

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/02d91e39-f517-4921-99a5-52036f0cb085)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/3d0b4883-4980-43ab-868c-e88a97e35f61)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/09d6a0d8-c1e8-45d0-b271-4206454fa968)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/a98f3be5-b90c-4c85-b2a1-c64a8d700a28)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/6a96eacb-c45b-4ba0-a0dc-f0c811dc9a13)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/157d8cec-618b-4306-be5f-e114d7a8fc15)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/ee44cc3f-2271-4d6b-ba3d-e8c8b38bf638)

### Task 5 : Ping

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/bcbf6f77-dafb-4c93-b5fb-cbc5fd4a6d89)

### Task 6 : Traceroute

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/a4846c3e-41af-4466-aaea-89f3f2d682c6)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/6fe14c01-1881-4247-8b4f-681beaaf03c1)

### Task 7 : WHOIS

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/9af968ac-0a5c-4b49-b1cc-1233f545c128)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/08d39fad-af74-40bf-8332-4dc913e5fe0b)

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/bd191aee-099e-4648-8c5b-afcfc93882a7)

### Task 8 : Dig

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/dc2ca8e7-4af7-4d24-938f-bc789dbc7ca4)

### Task 9 : Further Reading 

![image](https://github.com/yeuubonn2k4/TRYHACKME/assets/161863346/f88d4e83-ffea-4b15-a24b-e13bec13ead9)
