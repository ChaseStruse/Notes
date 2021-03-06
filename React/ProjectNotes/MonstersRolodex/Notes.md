# Monster Rolodex Notes

1. Began by running npx create-react-app monster-rolodex

2. Modified index.html to correctly reflect what is supposed to be displayed and removed unnecessary comments this can be found <a href="https://github.com/ChaseStruse/MonsterRolodex/commit/8cbe94eebfe7da41fe5b797550ae8370b5c99227"> here </a>

3. Modified App.js to be a class and added a button with state modification functionality. This can be found <a href="https://github.com/ChaseStruse/MonsterRolodex/commit/dc7fc1714490ea4208b6fc7a7650331617b4923d"> here </a>

4. Modified within App.js creating an array of monsters which contained an id and a name. These then get iterated and placed into h1 tags. Some key takeaways to know is that .map() iterates over every element of an array and does whatever function it is given, for example in our project we are telling it to display an h1 tag with the monsters name. Another key thing to note is that a map does not require a key but will throw a warning if you dont have one. This is what our id field is for. Keys are important because if the state of one of the objects is changed it is easier for React to identify the object. This can be found <a href="https://github.com/ChaseStruse/MonsterRolodex/commit/d1cc3d5f412529cb9d7601b5b019766cb7a03864"> here </a>

5. Within app.js fetched sample data from a url and displayed it. This uses the componentDidMount to fetch the data as soon as mounting is complete. This can be found <a href="https://github.com/ChaseStruse/MonsterRolodex/commit/60ef7e8d6e917af024711dc48d58275d6d13b5af"> here </a>

6. Created card-list component as well as style and used it in App.js. One thing to note here is that props.children is anything that is within the component call. This can be found <a href="https://github.com/ChaseStruse/MonsterRolodex/commit/7bf59f948197085ae4393548e8b9450680fa0597"> here </a> 

7. Added card component which allowed us to use image, email and name to make the card look a lot better. This can be found <a href="https://github.com/ChaseStruse/MonsterRolodex/commit/3ca9c1050c48771934a34b16f122d50550236334"> here </a> 

## Things to Note that really dont fit in the steps

LifeCycle Methods - Methods that get called at different stages when the component gets rendered. Ex: componentDidMount()