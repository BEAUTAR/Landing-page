<script>

    
    import { getAuth, signInWithPopup, GoogleAuthProvider } from "firebase/auth";
    import { initializeApp } from 'firebase/app';
    
    // TODO: Replace the following with your app's Firebase project configuration
    // For Firebase JS SDK v7.20.0 and later, measurementId is optional

    import { onMount } from "svelte";
   let provider 
   let auth
    onMount(() =>{
        const firebaseConfig = {
  apiKey: "AIzaSyCQJ-RliZe8V8M7LRAJqa6tzlLqxt1QKNs",
  authDomain: "landing-page-7972c.firebaseapp.com",
  projectId: "landing-page-7972c",
  storageBucket: "landing-page-7972c.appspot.com",
  messagingSenderId: "374238400975",
  appId: "1:374238400975:web:0fe6aef664f44e4d4382ba",
  measurementId: "G-70NVEG20S1"
};
    initializeApp(firebaseConfig);
     provider = new GoogleAuthProvider();   
     auth = getAuth();
    });
    
    let links = ["portfolio", "about me", "my blog", "reveiws", "contact me"];
    let imgs = ["twitter", "dribbble", "behance", "vimeo", "linkedin"];
    var topLine =['🔍Search', 'Sign in', 'Sign up']
    let exception = 0;
    function exceptSearch (){
       return topLine.pop(exception)
    };
   console.log(topLine.shift);

   
function signInWithGoogle() {
    signInWithPopup(auth, provider)
  .then((result) => {
    // This gives you a Google Access Token. You can use it to access the Google API.
    const credential = GoogleAuthProvider.credentialFromResult(result);
    const token = credential.accessToken;
    // The signed-in user info.
    const user = result.user;
    console.log(user);
    // ...
  }).catch((error) => {
    // Handle Errors here.
    const errorCode = error.code;
    const errorMessage = error.message;
    // The email of the user's account used.
    const email = error.email;
    // The AuthCredential type that was used.
    const credential = GoogleAuthProvider.credentialFromError(error);
    // ...
  });  
}

</script>

<nav class="navbar">
        <div class = 'logo'>
            <a href=".">
                <img src="./Logo.png" alt="Logo"/>
            </a>
        </div>

    <div class="nav-links">
        {#each links as link }
            <p>
                {link}
            </p>
        {/each}
    </div>

    <div class="socials">
        {#each imgs as pic}  
        <p><img src="./images/{pic}.png" alt="{pic}" /></p>
        {/each}
    </div>
   <div class="options">
        <button class='optnButton'>   
            🔍Search
        </button>
    
        <button on:click={signInWithGoogle} class="optButton">   
            Sign In
         </button>
    
    <a href="./SignUp">
        <button class='optsButton'>   
            Sign Up
         </button>
    </a>
    </div>  
</nav>

<style>
    .nav-links{
        position: fixed;
        display: flex;
        flex-direction: row;
        width: 1000px;
        left: 250px;
    }
    .options{
        position: fixed;
        display: flex;
        width: 600px;  
        left: 1000px; 
        flex-direction: row;
        font-weight: bold;
        transition: all 0.2s; 
         
    }   
    .options > button {
         margin-left: 1rem;
        margin-right: 1rem;
    }
    .optButton{
        background: #E2E8F0;
        color: rgb(39, 48, 61);
        border: solid rgb(97, 100, 104);
        border-radius: 15px;
         
    }
    .optsButton
    {
        margin-left: 10px;
        background: #E2E8F0;
        color: rgb(39, 48, 61);
        border: solid rgb(97, 100, 104);
        border-radius: 15px;
         
    }
    .optnButton{
        background: #E2E8F0;
        color: rgb(39, 48, 61);
        border: solid rgb(97, 100, 104);
        border-radius: 15px;
        width: 170px; height: 25px;
          
    }
    button:hover{
        cursor: pointer;
        background: rgb(125, 130, 136);
    }
        
    .logo{
        margin-left: 5rem;

    }
    .nav-links > p {
        margin-left: 1rem;
        margin-right: 1rem;
        font-weight: bold;
        transition: all 0.2s;
    }

    .navbar {
        background-color: #fff;
    }

    .socials {
        display:flex;
        align-content: space-between;
        flex-direction: row;
        position: fixed;
        left: 750px;
        transition: all 0.2s;
        width: 400px;
      
    }
    .socials > p {
        margin-left: 0.5rem;
        margin-right: 0.5rem
    }
    nav {
        display: flex;
        align-items: center;
        align-content: space-around;
        position:fixed;
        z-index: 100;
        }

    p:hover {
        color: #CB3322;
        cursor: pointer;
        transform: scale(1.1);
    }

    p:hover {
        transform: scale(1.5);
        cursor: pointer;
    }
    
   
</style>
