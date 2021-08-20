<template>
    <form v-on:submit="login">
    <div class="imgcontainer">
         <img src="https://www.w3schools.com/howto/img_avatar2.png" width="100" height="80"/>
    </div>
    <div class="container">
        <label for="uname"><b>Username</b></label>
        <br>
        <input type="text" placeholder="Enter Username" name="uname" required>
        <br>
        <label for="psw"><b>Password</b></label>
        <br>
        <input type="password" placeholder="Enter Password" name="psw" required>
        <br>
        <button type="submit">Login</button>
        <br>
        <label>
        <input type="checkbox" checked="checked" name="remember"> Remember me
        </label>
        <br>
        <router-link class="nav-link text-white" :to='"/signup"'>
            <button>Register</button>
        </router-link>
    </div>
    <div class="container" style="background-color:#f1f1f1">
        <button type="button" class="cancelbtn">Cancel</button>
        <span class="psw">Forgot <a href="#">password?</a></span>
    </div>
    </form>
</template>
<script>
import router from '../router'
import axios from 'axios'

export default {
    name: "Login",
    methods: {
        login: (e) => {
            e.preventDefault()
            let email = 'user@gmail.com'
            let password = 'password'
            let login = () => {
                let data = {
                    email: email,
                    password: password
                }
                axios.post("https://localhost:3000/api/login", data)
                .then((response) => {
                    console.log('Logged in.')
                    self.$set(this, "user", response.data.user)
                    router.push('/dashboard')
                    
                })
                .catch((error) => {
                    console.log("Cannot log in.")
                    router.push("/")
                })
            }
            login()

        }
    }    
}
</script>
<style scoped>
    /* Bordered form */
    form {
    border: 3px solid #f1f1f1;
    }

    /* Full-width inputs */
    input[type=text], input[type=password] {
        width: 50%;
        padding: 12px 20px;
        margin: 8px 0;
        display: inline-block;
        border: 1px solid #ccc;
        box-sizing: border-box;
    }

    /* Set a style for all buttons */
    button {
        background-color: #04AA6D;
        color: white;
        padding: 14px 20px;
        margin: 8px auto;
        border: none;
        cursor: pointer;
        width: 50%;
    }

    /* Add a hover effect for buttons */
    button:hover {
        opacity: 0.8;
    }

    /* Extra style for the cancel button (red) */
    .cancelbtn {
        width: auto;
        padding: 10px 18px;
        background-color: #f44336;
    }

    /* Center the avatar image inside this container */
    .imgcontainer {
        text-align: center;
        margin: 24px 0 12px 0;
    }

    /* Avatar image */
    img.avatar {
        width: 40%;
        border-radius: 50%;
    }

    /* Add padding to containers */
    .container {
        padding: 16px;
    }

    /* The "Forgot password" text */
    span.psw {
        float: right;
        padding-top: 16px;
    }

    /* Change styles for span and cancel button on extra small screens */
    @media screen and (max-width: 300px) {
        span.psw {
            display: block;
            float: none;
        }
        .cancelbtn {
            width: 100%;
        }
    }
</style>