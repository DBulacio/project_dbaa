<template>
   <div class="container"> 
        <input v-model="this.inputName" type="text">Name:
        <input v-model="this.inputPassword" type="password">Password:
        <button :disabled="this.disableButton" @click="login()">{{loginButton}}</button>
        <PopUp :color="this.popUpColor" :text="this.popUpText"/>
    </div>

</template>

<script>
import { defineAsyncComponent} from 'vue';

    export default {
        
        data() {
            return {
                password: "1234",
                userName: "Alberto",
                loginButton: "Login",
                disableButton: false,
                inputName: "",
                inputPassword: "",
                popUpColor: "",
                popUpText: ""
            }
        },
        methods: {
            login() {
                this.disableButton = true
                if (this.inputName === this.userName && this.inputPassword === this.password){
                    this.loginButton = "Loading"
                    this.popUpColor = "green"
                    this.popUpText = "Bienvenido"
                }
                else {
                   
                    this.disableButton = false
                    this.inputName = ""
                    this.inputPassword = ""
                    this.popUpColor = "red"
                    this.popUpText = "Login incorrecto"
                }           
            }
        },
        components: {
      PopUp: defineAsyncComponent(() => import ('./PopUp.vue'))
        }
    }
</script>

<style scoped>
.container {
  display: flex;
  flex-direction: column;
  margin: 5px;
}

</style>