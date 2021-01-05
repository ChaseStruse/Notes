# Setting up your react app!

Step 1: npx create-react-app appname

Guess what? That's it, no really thats it.

Starting up the project: yarn start or npm start

Place to look at would be package.json. This where you can find the start, build, test, and eject functions. When you use yarn start it calls that package json and runs the start script. This is good to know if you need to add different scripts for different jobs. 

create-react-app uses Babel and webpack to convert react to a working html file. Babel ensures that the app will work on all of the browsers no matter how old or new. Webpack allows us to write modular code which means it takes all of our JS files and packs them into smaller files so it is optimized. 

