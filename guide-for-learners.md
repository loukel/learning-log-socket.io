# Utilising Sockets with React (Socket.IO)

![image](https://user-images.githubusercontent.com/65136145/165337658-0c527fa4-2116-4484-b006-b52ad83dda9d.png)

## Table of contents
- [Motivation](#motivation)
- [Background](#background)
    - [Node](#node)
    - [React](#react)
    - [Redux](#redux)
- [Learning Materials](#learning)
- [Evaluation](#evaluation)

## Motivation <a name="motivation"></a>
Sockets are incredible powerful; it enables multiple users to manipulate data at once, where each user see's live changes. Combining sockets with React provides an extremely powerful development environment where a web app can be split up into components while sockets provide an excellent user experience. Live correspondance with servers seem to be the future of web apps especially for apps that are used for teams which seems to be a rising trend in apps. There's apps like Asana, Notion, Monday and soo many others which all utilise sockets. Social media sites also utlise sockets - you wouldn't want to refresh the page just to see if you've received a message or if someone has just posted. Therefore, to be a web developer in this current paradigm its imperative that you become comfortable using sockets.

## Background <a name="background"></a>
(What do you need to know before starting? Include links to material to catch up. Make it clear who your target audience is)
The following technologies are important to know before trying to pick socket.IO up, its important note that all technology stacks allow for sockets (polling) but using Sockets with React and Node (Express) is the the most up to date method to use socket.IO with and there is a lot more support online (resources, Stackoverflow answers, YouTube tutorials etc.).

Socket.IO works with the following server implementations:
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

More details on this can be found [here](https://socket.io/docs/v4/)

### Node <img src='/icons/node.svg' width='20px'> (Express) <a name="node"></a>
It's important to understand how to use Node JS with Express as this is where you will be setting up the server implementation of sockets. The best way to learn sockets would be to watch and follow this [Node YouTube Tutorial Playlist](https://www.youtube.com/watch?v=zb3Qk8SG5Ms&list=PL4cUxeGkcC9jsz4LDYc6kv3ymONOKxwBU). As a bonus it would help to go over the [documentation](https://expressjs.com/) when struggling. But just these two resources will enable you to become comfortable with Node and Express. It may be worth learning how to connect a database up with the server, I used Prisma, this is the [documentation](https://www.prisma.io/), but any other of your prefered database technology would be fine.

### React <img src='/icons/react.svg' width='20px'> <a name="react"></a>
React enables a web application to be split up into components which makes it easy to add functionality and the modularisation of Javascript and HTML (JSX) helps to provide a maintable environment. The best YouTube tutorial series would [this](https://www.youtube.com/watch?v=j942wKiXFu8&list=PL4cUxeGkcC9gZD-Tvwfod2gaISzfRiP9d)

### Redux <img src='/icons/redux.svg' width='20px'> <a name="redux"></a>
Redux is an excellent technology that enables developers to store and update data in the global state. This reduces the complexity of individual components, it also allows for components to only contain the functionality and data that it is involved with. With sockets, its hard to understand whats going on straight away, so mixing this with component complexity would further complicate the issue so utilising redux with sockets really makes code easier to understand and manage. Its an elgantly way to store data in React. The best way to learn would be to watch this [YouTube Tutorial Series](https://www.youtube.com/watch?v=OxIDLw0M-m0&list=PL4cUxeGkcC9ij8CfkAY2RAGb-tmkNwQHG) and go over the [documentation](https://redux.js.org/).

## Learning Materials: Provide appropriate links to external resources with commentary <a name="learning"></a>
The best way to understand the general idea of sockets would be to watch [this](https://www.youtube.com/watch?v=1BfCnjr_Vjg) which is a short overview of sockets. The documenation for Socket.IO is incredibly detailed, concise and easy to understand, I highly recommend always refering to as you go along your learning venture. https://socket.io/docs/v4/. I would recommending pursuing a project to learn sockets as it provides a goal and therefore motivation to learn. The best example project would be to build a chat room, this is a [Good Example of How to Build a Chat Room](https://medium.com/swlh/chat-rooms-with-socket-io-25e9d1a05947). Some other good tutorials that I would highly recommend would be this Tutorial on [How to Send Data with Socket IO with React](https://www.youtube.com/watch?v=9HFwJ9hrmls), this video helps to give you great understanding on how to practically use Socket IO. For example, he introduces the way you test sockets, with two private windows.

### Server Sided
- **Set up and integration:** I recommend going through this [Socket.IO Documentation Page](https://socket.io/get-started/chat#integrating-socketio).
- **Rooms** are extremely important, rooms enable users connected to sockets to be split up into groups. Once in groups data can be send to specific groups and groups can update the data for other users in that group. This documentation page is incredibly detailed and will help you to understand how to integrate rooms [Socket Room Documentation](https://socket.io/docs/v3/rooms/).
- **Sending Messages:** It's very important to distinguish the difference between using sockets and IO to send messages, there's a really detailed Stackoverflow post on this [here](https://stackoverflow.com/questions/32674391/io-emit-vs-socket-emit). One method allows for data to be send to the room not including the socket send the original message and the other sends to the whole room.

### Client Sided 
- **React with Sockets:** This is the [documentation for how initiate sockets client side](https://socket.io/docs/v4/client-installation/). I'd also like to iterate a video I previously mentioned which is [Real Time Data Sending with SocketIO](https://www.youtube.com/watch?v=CgV8omlWq2o) which is effective in detailing how to integrate React with sockets.
- **Redux with Sockets:** I utilised multiple sources to figure out the best way to use Redux with sockets and so I recommend going over my repository [Kanban Board with Sockets](https://github.com/loukel/KanbanBoard/tree/sockets-redux/client/src) **(ensure that you are on the sockets-redux branch)** and going through the reducers, actions and service files. It also contains the server side code so it will help understanding how it connects. You will then be able to modify the functions to your own purpose.

## Evaluation: <a name="evaluation"></a>
(How useful is the skill, compared with the effort of learning it? What similar alternatives are there?)
### Sockets vs REST
REST (Representational State Transfer) describes an architectual style for APIs, an API allows for clients to connect up with a server. This usally works by the client sending a request (which could be a ny of the methods: GET, POST, PUT, DELETE) and the server returning a response. This can be seen below in the diagram.
![image](https://user-images.githubusercontent.com/65136145/165501072-b6058c12-adad-494c-b023-ba7267be323b.png)
*(from https://phpenthusiast.com/blog/what-is-rest-api)*
![image](https://user-images.githubusercontent.com/65136145/165497187-72a8fb13-eec5-4ac1-82d3-c3f99795d53f.png)
*(from https://socket.io/docs/v3/how-it-works/)*

### Socket.IO vs WebSocket API
The main alternative to using sockets would be to using a REST api, the disavantage of this compared to this sockets would the fact

- research sockets vs REST
- (diagrams)
- WebSocket API vs Socket IO
- Found it quite easy to learn but hard to structure files avoid it
- Definetly worth learn - future of web development

## A presentation mark (10%) will be awarded on the basis of
- formatting in ￿GitHub flavored) Markdown
- choice of media (images, video)
