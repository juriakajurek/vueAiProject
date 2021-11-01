<template>
  <div class="login">
    <div class="view">
      <div class="login-form">
        <h2>Logowanie</h2>
        <input
          type="text"
          name="username"
          v-model="input.username"
          placeholder="Nazwa użytkownika"
        />
        <input
          type="password"
          name="password"
          v-model="input.password"
          placeholder="Hasło"
        />
        <Button v-on:click="login()" text="Zaloguj"></Button>
      </div>
    </div>
  </div>
</template>


<script>
import Button from "../components/Button";

export default {
  name: "Login",
  data() {
    return {
      input: {
        username: "",
        password: "",
      },
    };
  },
  components: {
    Button,
  },
  methods: {
    login() {
      if (this.input.username != "" && this.input.password != "") {
        if (
          this.input.username == this.$parent.mockAccount.username &&
          this.input.password == this.$parent.mockAccount.password
        ) {
          this.$emit("authenticated", true);
          this.$router.replace({ name: "secure" });
        } else {
          console.log("The username and / or password is incorrect");
        }
      } else {
        console.log("A username and password must be present");
      }
    },
  },
};
</script>


<style lang="less" scoped>
.login {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  .view {
    width: 100%;
    height: 80vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    .login-form {
      width: 20vw;
      display: flex;
      flex-direction: column;
      input {
        margin: 0.3rem;
        margin-left: 0.5rem;
        margin-right: 0.5rem;
        padding: 0.5rem;
        border-radius: 0.5rem;
        background-color: white;
      }
    }
  }
}
</style>