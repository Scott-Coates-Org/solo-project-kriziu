[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-c66648af7eb3fe8bc4f294546bfd86ef473780cde1dea487d3c4ff354943c9ae.svg)](https://classroom.github.com/online_ide?assignment_repo_id=8182727&assignment_repo_type=AssignmentRepo)
# React Solo Project

## Requirements

- `React.js 18`
- `Node.js ^16.10 || 18`. Need to change your version?
  - [Window](https://github.com/coreybutler/nvm-windows)
  - [Mac](https://github.com/tj/n)
- Firebase (optional, but strongly encouraged for your database, auth, hosting, and storage needs).
- Hosting: if not Firebase, it must be an pre-approved PaaS
  - Vercel
  - Heroku
  - Railway

## Getting Started

We are using "yarn" instead of "npm" in this project.

1. Install yarn. `npm install -g yarn`
2. Install all node modules. `yarn install`
3. Boot up the server. `yarn start`

### Hosting (Necessary for sprint 1)

1. Go to the official Firebase website and set up a project.
2. Enable Firebase Hosting by going into the hosting section under Build dropdown.
3. Inside your repo run the following commands (one at a time):
4. `npm install -g firebase-tools`
5. `firebase login`
6. `firebase init`
7. `yarn build` (*remember to always build before deploying your code to production*).
8. `firebase deploy`
9. If you run into trouble take a look at: https://www.geeksforgeeks.org/how-to-deploy-react-project-on-firebase/

### Firebase (if you need authentication or a database in your project)

1. If you don't need authentication or a db, you can ignore the 'login', 'firebase' and 'authSlice' files and skip this section.
2. Go to the official Firebase website and set up a project.
3. Enable Firebase Firestore if you need a database or Firestore Authentication if you need user authentication.
4. If you need user authentication, make sure to enable google authentication in the settings.
5. If you used `yarn` to install all dependencies, you shouldn't need to install anything else.
6. Change the name of the '.env.local.example' file to '.env.local' and write your api key and other information (can be found in the settings of your project on the firebase website).
7. The 'Login' component is commented out in 'App.js'. If you don't need it, delete it. If you do need it, move it to the page where you need it.
8. You can import the 'Login' component on the page you want the user to log in. At the moment the logic is set up to support authorization with Google. If you want to add others (email, username and password, github) You will have to implement this on your own.
9. Clicking on the "Continue with Google" button should open a pop-up that logs you in. If this doesn't work, check your firebase keys and if you have google authentication enabled. Once you are logged in, it will automatically update the state in the 'authSlice' reducer with your information (display name, email and access token). If you need any of these, you can get them with a useSelector hook in the component where you need them.
10. You can check if the user is signed in by checking the state of the 'authSlice'. If user is false (empty), the user isn't signed in.
11. You are free to style the buttons or the login component as you see fit. You can (probably a good idea) move the log out button somewhere else, depending on your project. as long as you import all the necessary things and don't change the function/logic, it should work.

### Folder Structure And Advice

1. You can adjust the folder structure if you have other preferances.
2. The "redux" folder contains an example reducer (counter). You can delete this.
3. You can use whichever CSS library you wish, or just plain CSS/SASS (preferably modules).
4. You may modify the boilerplate (e.g. delete dummy text in App.js, the counter, the the logo.svg, etc.)
5. V1 of this project is due in 3 weeks. Remeber to KISS (Keep It Simple, Stupid). You need to think of v1 as a conceptual boundary of constraints; anything *outside those boundaries must be saved for a future version*.

<!---
*** WHEN YOU ARE UP AND RUNNING, YOU MAY DELETE EVERYTHING ABOVE -EXCEPT- THE VERY TOP LINE. ***
-->

## Sprint Progress

Go to the [milestones tab](../../milestone/1) to track your progress.

## Project Overview

### Public URL

[https://ballzone.herokuapp.com](https://ballzone.herokuapp.com)

### Description

ballzone - 2D (top-down perspective) real-time game with 2 teams where players try to score a goal and win (like in soccer or hockey).

Sprint 1:
- Creating room and receiving id
- Rendering board where player can move
- Moving via keys (WSAD)

Sprint 2:
- Joining other room by id and connecting with all players
- Real-time moving
- Collisions with other players

Sprint 3:
- Ball
- Ball physics:
    - Moving ball when collision with it is detected
    - Shooting ball when player is close enough and space key is pressed
- Scoring system
- End match when time is over
- Math results (which team won, how many scores per player, etc.)

In v1 version you will be able to create room match and other players will be able to join it. When match starts you will move via keys. All players and ball will move with you in real-time and when someone will score a goal system will detect that and give a point to a team. Match ends when time has elapsed and everyone sees results.

### Mockups

![Home page](/mockups/home.jpg)
![Game page](/mockups/game.jpg)
![Statistics](/mockups/stats.jpg)
