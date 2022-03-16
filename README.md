# Learning Log For improving at React and Sockets

## Widgets and introduction(16/03/22)

I work as a web developer for a company in a team of web developers who are creating a web app for fellow videographers to help manage everything related to their projects. My goal for this learning venture is to improve my skills in React and sockets. I'm hoping that from improving my knowledge and experience using React and sockets I can create a concise and efficient guide for learners so that my web developer associates can use it to utilise sockets with React. I aim to complete two components in the following order:
- Widgets Dashboard: for the home page of the app, users should be able to view widgets relating to different aspects of the app: budgets, equipment, projects etc. I want to be able to use React to create a dashboard for this. My goal is to set it up for the future so uses can drag different size cards about in a grid. Therefore, this can later be used to display the actual widgets where the user can move to them to view an overview of whats going on with their business.
- Kanban Board for project states: I've previously created a drag and drop kanban board where project states are displayed and can be changed. However, there is an issue when multiple users are editing the project states at the same time. I will need to implement sockets into the site, which will require knowledge of using sockets in the back-end and the front-end with React. I plan to ensure that the code readable and understandable to other web developers in the team that I am working with so that they can understand it and hopefully reuse some of the code for elsewhere in the app. I'm expecting that this part will be split up in several entries.
There may be other components of the web app that may need to be completed to achieve my goal of improving my skills in React and sockets. It will depend on the demands of what the team wants to achieve for the app.
My general goal is to add as many features to the web app so that they can release a minimum viable product as quickly as they can.

### Working on the widgets dashboard
To allow users to drag and drop cards on the dashboard, I first had to reseach react compatible drag and drop packages. The best one I could find was [react-grid-layout](https://react-grid-layout.github.io/react-grid-layout/examples/0-showcase.html). I learned how to use it by going through all of their examples and tried to apply to the dashboard I wanted to create. I then had to use it with React and bootstrap. I learned how to do this using trial and error trying different things out until it worked accordingly. The documentation wasn't too detailed so it so I had to go through the source code of the examples and try to understand how it works.
Here is the pull Request I created, which was approved by Elliot, a team member who went over my code approved it, then merged it into the project. We collaborated by him checking the code and merging it, which is a great habbit to prevent issues in the future if there is some code that could malicously affect the rest of the project.
![Pull Request for widgets](/screenshots/widgets-pr.png)
This is the main code for the widgets.
![The main code used for the widgets](/screenshots/widgets-code.png)
This is what the widgets dashboard looked like.
![What it looked like](/screenshots/widgets-view.png)
Completing the widgets dashboard, mainly enabled me to learn about available react drag and drop packages and how to use them, mainly react-grid-layout. For this learning venture, I hope to learn more about React and sockets in my next entry so I can achieve my goal of improving my knowledge and experience in React and sockets.
