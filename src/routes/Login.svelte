<script>
import { getAuth, signInWithPopup, GoogleAuthProvider } from "firebase/auth";
const provider = new GoogleAuthProvider();   
const auth = getAuth();
function signInWithGoogle() {
    signInWithPopup(auth, provider)
  .then((result) => {
    // This gives you a Google Access Token. You can use it to access the Google API.
    const credential = GoogleAuthProvider.credentialFromResult(result);
    const token = credential.accessToken;
    // The signed-in user info.
    const user = result.user;
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



<div class= 'welcome'>
<h1 >
 Welcome to Kamilia
</h1>
<h1 class = 'call'>
Kamilia is a leading website for fashion design display
</h1>
<div class = 'inputt'>
<form action="Email"class= 'email'>
    Email 
<input type= "Email" >
</form>
<form action=""class= 'emails'>
    Password
<input type= "password" >
</form>
</div>
    <button on:click= {loginWIthGoogle} class = 'googlebtn'>
    Sign in with Google
    </button> 
<button class = 'googlebtn'>
    Sign in with Twitter
</button>
<button class = 'googlebtn'>
    Sign in with Facebook
</button>
    <a href ="">
        Forgot Password?
    </a>

</div>
<style>
    .welcome{
        display:flex;
        flex-direction:column;
        align-items:center;
        position: absolute;
        background-color: grey;
        top: 200px;
        width: 500px;
        left: 450px;
    }
    .email{
        width: 300px;
        height: 25px;
        left: 50px;
    }
    .emails{
        width: 345px;
        height: 25px;  
    }
    .inputt{
        display:flex;
        flex-direction: column;
        align-items: center;
    }
    .inputt > input {
        margin-top: 2px;
        margin-bottom: 2px;
    
    }
    .googlebtn{
        width: 350px;
        height: 30px;
        border-radius: 30px;
    }
    .welcome > h1 {
      
        padding-top: 1px;
        padding-bottom: -10px;
    }
    .call{
        font-size: 15px;
    }
    .welcome > button {
        margin-left: 1rem;
        margin-right: 1rem;
    }
</style>