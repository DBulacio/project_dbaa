<template>
   <div class="container"> 
            <input v-model="this.inputName" type="text">Name:
            {{ this.inputName }}
            <input v-model="this.inputPassword" type="password">Password:
            <button :disabled="this.disableButton" @click="login()">{{loginButton}}</button>
        
    </div>

</template>

<script>
    export default {
        data() {
            return {
                password: "1234",
                userName: "Alberto",
                loginButton: "Login",
                disableButton: false,
                inputName: "",
                inputPassword: ""

            }
        },
        methods: {
        login() {
            
            this.disableButton = true
            if (this.inputName === this.userName && this.inputPassword === this.password){
                console.log("Bienvenido ahre")
                this.loginButton = "Loading"
            }
            else {
                console.log("Dale wahcin...")
                this.disableButton = false
                this.inputName = ""
                this.inputPassword = ""
            }
            
        }
    }
}
    

</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  margin: 5px;
}

</style>