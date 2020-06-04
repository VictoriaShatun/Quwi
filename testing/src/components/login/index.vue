<template>
  <div>
    <section class="container">
      <div class="user-login">
    <form class="box" @submit.prevent="login">
      <ul>
        <li>
          <router-link class="brand" to="/">
            <img src="../../assets/quwi-logo.png" width="40px" />
          </router-link>
          <h1>QUWI</h1>
        </li>
      </ul>
      <div class="active-input skin-guest">
        <div class="input-group">
          <div class="input">
            <div class="placeholder top-text" style="">
        Email
      </div>
            <input required
                   v-model="username"
                   type="text"
                   placeholder="Email"
                   autofocus="autofocus"/>
          </div>
        </div>
      </div>
      <div class="active-input skin-guest">
        <div class="input-group">
          <div class="input">
            <div class="placeholder top-text" style="">
              Password
            </div>
        <input
          required
          v-model="password"
          type="password"
          placeholder="Password"
        />
          </div>
        </div>
      </div>
      <div class="button">
        <button class="btn" type="submit">Login</button>
      </div>
           <div>
        <a href="/forgot" class="">Forgot password?</a>
      </div>
    </form>
      </div>
      </section>
  </div>
</template>

<style>
.container {
  min-height: calc(100vh - 46px);
  display: flex;
  align-items: center;
}
.user-login {
  width: 440px;
  margin: auto;
  text-align: center;
}
.user-login .box {
  padding: 25px 40px 35px;
  background: #fff;
  border: 1px solid rgba(0, 0, 0, .11);
  box-shadow: 0 0 12px rgba(0, 0, 0, .25);
  border-radius: 15px;
}

form {
  display: block;
  margin-top: 0em;
}
.user-login .button .btn {
  margin-bottom: 20px;
}

.user-login .box .btn {
  background: #2668c1;
  height: 52px;
  width: 100%!important;
  text-transform: none;
  text-shadow: none;
  font-size: 18px;
  border-radius: 9px;
  font-weight: 400;
  margin-top: 17px;
}
.btn {
  display: inline-flex;
  justify-content: center;
  align-items: center;
}
.btn {
  height: 34px;
  padding: 0 15px;
  text-transform: uppercase;
  font-size: 11px;
  color: #fff;
  font-weight: 700;
  text-shadow: 1px 1px 1px rgba(0,0,0,.5);
  background: #395378;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  outline: none;
}
.user-login .box .active-input {
  margin-bottom: 12px;
}
.active-input .input-group .input {
  position: relative;
  width: 100%;
}
.active-input.skin-guest .input-group .input .top-text.placeholder {
  color: #999;
}
.active-input .input-group .b-input .top-text.placeholder {
  color: #4b84da;
}
.active-input .input-group .input .top-text {
  margin: 0 10px;
  max-width: calc(100% - 20px);
  position: absolute;
  top: -.55em;
  background: #fff;
  display: block;
  float: left;
  padding: 0 3px;
  white-space: nowrap;
  text-overflow: ellipsis;
  overflow: hidden;
}
.active-input.m-skin-guest .input-group .input input,
.active-input.m-skin-guest .input-group .input textarea {
  border: 1px solid #dadada;
  border-radius: 5px;
}

.user-login .box input[type=""],
.user-login .box input[type=password],
.user-login .box input[type=text] {
  border: 1px solid #4b84da;
  border-radius: 5px;
  padding: 15px;
  width: 100%;
  outline: none;
}
input, select, textarea {
  font-size: inherit;
  font-family: inherit;
}
.user-login .box .active-input {
  margin-bottom: 12px;
}



</style>

<script>
import { AUTH_REQUEST } from "actions/auth";

export default {
  name: "login",
  data() {
    return {
      username: "dogo",
      password: "dogy"
    };
  },
  methods: {
    login: function() {
      const { username, password } = this;
      this.$store.dispatch(AUTH_REQUEST, { username, password }).then(() => {
        this.$router.push("/");
      });
    }
  }
};
</script>
