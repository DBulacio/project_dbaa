<template>
  <div class="login">
    <h1>Login</h1>
    <LoginForm />
  </div>
</template>

<script>
  import { defineAsyncComponent} from 'vue';
  export default {
    components: {
      LoginForm: defineAsyncComponent(() => import ('../components/LoginForm.vue'))
    }
  }
</script>

<style scope>
@media (min-width: 1024px) {
  .login {
    min-height: 100vh;
    display: flex;
    align-items: center;
    margin: 5px;
  }
}

</style>
