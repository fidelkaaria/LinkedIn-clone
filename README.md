# LinkedIn build with Redux,React and Firebase

Project Link - https://linkedin-ff033.web.app



## Tools used
* npx create-react-app linkedin-clone --template redux
* Install Firebase
* npm install -g firebase-tools
* Install Material UI Core and Icons
* npm install @material-ui/core
* npm install @material-ui/icons

 &mdash; Search Material UI Icons
 
&mdash; https://material-ui.com/components/material-icons

* Install React Flip Move
* npm install --save react-flip-move

&mdash; nice animations for list components (user posts)

&mdash; https://joshwcomeau.github.io/react-flip-move


### Code Snippet

#### Grabbing the user posts from Firestore and passing them into State within our app as an array [] of posts

  function Feed() {

      const [posts, setPosts] = useState([]);

      useEffect(() => {
          
              db.collection('posts').onSnapshot((snapshot) => 
                              
                  setPosts(snapshot.docs.map((doc) => (       
                      {
                          id: doc.id,
                          data: doc.data()
                      }
                  ))
              ));
      }, []); 

      ...
  }
