# Utilising Sockets with React
*Socket.IO is the most up to date technology for sockets, this will be the focused technology in this learning guide.*

![image](https://user-images.githubusercontent.com/65136145/165337658-0c527fa4-2116-4484-b006-b52ad83dda9d.png)

(Image from https://medium.com/react-world/use-socket-io-with-your-react-native-app-context-api-504813b4a4b7)

## Table of contents
- [Motivation](#motivation)
- [Background](#background)
    - [Node](#node)
    - [React](#react)
    - [Redux](#redux)
- [Learning Materials](#learning)
- [Evaluation](#evaluation)

## Motivation <a name="motivation"></a>
Sockets are incredible powerful; it enables multiple users to manipulate data at once, where each user see's live changes. Combining sockets with React provides an extremely powerful development environment where a web app can be split up into components while sockets provide an excellent user experience. Live correspondance with servers seem to be the future of web apps especially for apps that are used for teams which seems to be a rising trend in apps. Apps such as Asana, Notion, Monday and soo many more all utilise sockets and its certainly key to the user experience that they provide. Social media sites also heavily utlise sockets - you wouldn't want to refresh the page just to see if you've received a message or if someone has just posted. Therefore, as a web developer its imperative that you become comfortable using sockets in this current paradigm.

## Background <a name="background"></a>
The following technologies are important to know before trying to pick Socket.IO up, its important to note that all technology stacks allow for sockets but using Sockets with React and Node (Express) is the most modern and popular technology stack which results in there being a lot more support online (resources, Stackoverflow answers, YouTube tutorials etc.), making it easy to integrate.

However, Socket.IO works with the following server implementations:
- JavaScript
- Java
- Java
- Python

And client implementations in most major languages:
- JavaScript
- Java
- C++
- Swift
- Dart
- Python
- .Net
- Golang
- Rust
- Kotlin

(This has been copied from the official Socket.IO documentation)

More details on this can be found [here](https://socket.io/docs/v4/)

### Node <img src='/icons/node.svg' width='20px'> <a name="node"></a>
It's important to understand how to use Node JS as this is where you'll be setting the initation of the server implementation of sockets. The best way to learn sockets would be to watch and follow this [Node YouTube Tutorial Playlist](https://www.youtube.com/watch?v=zb3Qk8SG5Ms&list=PL4cUxeGkcC9jsz4LDYc6kv3ymONOKxwBU). As a bonus it would help to go over the [documentation](https://nodejs.org/en/docs/) when struggling. But just these two resources will enable you to become comfortable with Node. It may be worth learning how to connect a database up with the server, I used Prisma, here's the [documentation](https://www.prisma.io/), but any other of your prefered database technology would be fine.

### React <img src='/icons/react.svg' width='20px'> <a name="react"></a>
React enables web applications to be split up into components which makes it easy to add functionality and modularise JavaScript and HTML (JSX) which helps to provide a maintable environment. The best YouTube tutorial series would be [this](https://www.youtube.com/watch?v=j942wKiXFu8&list=PL4cUxeGkcC9gZD-Tvwfod2gaISzfRiP9d) which goes through a simple project to help understand the core of React. Generally it takes a lot of time working on projects to become familiar with React and so I recommend exploring it by completing different projects or you could go straight into a project with sockets but the learning process would be quite intense, but if motivated it would be a quick way to become comfortable with sockets and React.

### Redux <img src='/icons/redux.svg' width='20px'> <a name="redux"></a>
Redux is an excellent technology that enables developers to store and update data in the global state of React. This reduces the complexity of individual components, components therefore only contain the functionality and data that it is involved with. With sockets, its hard to understand whats going on from looking at code, so mixing this with component complexity would further complicate the issue of unreadable code so utilising redux with sockets really makes code easier to understand and manage. Its an elgant way to store data in React. The best way to learn Redux would be to watch [YouTube Tutorial Series](https://www.youtube.com/watch?v=OxIDLw0M-m0&list=PL4cUxeGkcC9ij8CfkAY2RAGb-tmkNwQHG) and go over the [Documentation](https://redux.js.org/).

## Learning Materials: Provide appropriate links to external resources with commentary <a name="learning"></a>
The best way to understand the general idea of sockets would be to watch [this](https://www.youtube.com/watch?v=1BfCnjr_Vjg) which is a short overview of sockets (100 seconds). The [Documentation for Socket.IO](https://socket.io/docs/v4/) is incredibly detailed, concise and easy to understand, I highly recommend refering to this as you go along with your learning venture. I would recommend pursuing a project to learn sockets as it provides a goal and therefore motivation to learn. The best example project would be to build a chat room, this is a [Good Example of How to Build a Chat Room](https://medium.com/swlh/chat-rooms-with-socket-io-25e9d1a05947). Some other good tutorials that I would highly recommend would be this [Tutorial on How to Send Data with Socket IO with React](https://www.youtube.com/watch?v=9HFwJ9hrmls), this video helps to give you gain an understanding on how to practically use Socket.IO. For example, he introduces the way you test sockets - with two private windows representing multiple clients.

### Server Sided
- **Set Up and Integration:** I recommend going through this [Socket.IO Documentation Page](https://socket.io/get-started/chat#integrating-socketio) which overviews how to implement Socket.IO.
- **Rooms** are extremely important, rooms enable users connected to sockets to be split up into groups. Once in groups, data can be send to specific groups and users can update the data for other users in that group. This documentation page is incredibly detailed and will help you to understand how to integrate rooms - [Socket Room Documentation](https://socket.io/docs/v3/rooms/).
- **Sending Messages:** It's very important to distinguish the difference between using socket and IO to send messages, there's a really detailed Stackoverflow post on this [here](https://stackoverflow.com/questions/32674391/io-emit-vs-socket-emit). One method allows for data to be send to the room not including the socket send the original message and the other sends to the whole room.

### Client Sided 
- **React with Sockets:** This is the documentation for [How to Initiate Sockets on the Client Side](https://socket.io/docs/v4/client-installation/). I'd also like to iterate a video I previously mentioned which is [Real Time Data Sending with SocketIO](https://www.youtube.com/watch?v=CgV8omlWq2o) which is effective in providing the methods of implementing sockets.
- **Redux with Sockets:** I utilised multiple sources to figure out the best way to use Redux with sockets and so I recommend going over my repository [Kanban Board with Sockets](https://github.com/loukel/KanbanBoard/tree/sockets-redux/client/src) **(ensure that you are on the sockets-redux branch)** and going through the reducers, actions, service and component files. It also contains the server side code so it will help understanding how it all connects. You will then be able to modify the functions and code to your own purpose.

## Evaluation: <a name="evaluation"></a>

### Socket Alternatives
**Sockets vs REST**
REST (Representational State Transfer) describes an architectual style for APIs, an API allows for clients to connect up with a server. This usally works with the client sending a request (which would be of the methods: GET, POST, PUT, DELETE) and the server returning a response. This can be seen below in the diagram. Generally a REST API works in a request/response methodology
![image](https://user-images.githubusercontent.com/65136145/165542504-ea9e69f1-7164-4134-a639-7e3143d111b9.png)

*(from https://phpenthusiast.com/blog/what-is-rest-api)*

Sockets connect clients up with the server but differ from REST APIs in the way that they provide a continuous connection where messages are received and sent. Sockets work in a full duplex methodology.
![image](https://user-images.githubusercontent.com/65136145/165497187-72a8fb13-eec5-4ac1-82d3-c3f99795d53f.png)

*(from https://socket.io/docs/v3/how-it-works/)*

|<img width="1000" height="1">Sockets<img width="1000" height="1">|<img width="1000" height="1">REST API<img width="1000" height="1">|
|----------|:-------------:|
| Faster response |  Slower response|
| Only vertical scaling available - to improve the performance you can't increase the amount of servers, you can only increase the hardware quality |  All scaling options available |
(source: https://ipwithease.com/web-socket-vs-rest/)
| Protocol |  Architecture |
| Requires memory and buffer to store data |  Requires fewer resources |
| Suitable for real time apps |  Permits many data types: plain text, html, json |

In my opinion its best to use Sockets when you require a real time app whereas if just simple requests are required then a REST API would be more suitable due to the formal architecture it provides, sockets can be hard to modularise and split up whilst its very easy to split up the endpoints of a REST API.

### How Useful is Integrating Sockets? 
Sockets enable a web app to interact with a database in real time, allowing for multiple users to work on the same entities at once. Sockets are extremely simple to integrate and once set up, its very easy to add more functions. There's not too much to learn to be able to integrate sockets into a web app, especially if you are very comfortable with the techonologies that the sockets are being integrated with.

A good example of the applications of sockets, which show how useful they can, would be this Kanban Board:

https://user-images.githubusercontent.com/65136145/165566398-0a659e0b-5300-45e2-a792-197e38c27d21.mov

This feature tracks the order of items in columns and the order of columns using multiple linked lists. If the feature used a REST API to store and maniplulate the data, then if one user updated the order of either the items or columns then the other users who have already fetched the board wouldn't know the most up to date order and therefore the new linked list data. If these other users try to update the board with the previous linked list order then it is likely to cause the list to become corrupt - meaning the data can't be rendered due to a corrupt linked list causing an illogical order. Sockets fixes this by enabling real time updates so that every user has the most up to date data.
