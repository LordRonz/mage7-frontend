<template>
  <div class="login-page">
    <div class="logo">
      <img src="/img/mage-white.png" />
      <h1 class="text-white d-inline-block">ANAVA</h1>
    </div>
    <div class="login-container shadow">
      <h1>Ganti Sandi</h1>
      <div>
        <label>Sandi</label>
        <input
          type="password"
          name="password"
          placeholder="Ketik disini..."
          v-model="user.password"
        />
      </div>
      <div>
        <label>Konfirmasi Sandi</label>
        <input
          type="password"
          name="password"
          placeholder="Ketik disini..."
          v-model="user.passwordConfirmation"
        />
      </div>
      <input
        type="submit"
        name="login"
        class="mt-4"
        value="Ganti"
        @click="changePassword()"
      />
    </div>
    <vue-particles
      color="#dedede"
      :particleOpacity="0.7"
      :particlesNumber="80"
      shapeType="circle"
      :particleSize="4"
      linesColor="#dedede"
      :linesWidth="1"
      :lineLinked="true"
      :lineOpacity="0.4"
      :linesDistance="150"
      :moveSpeed="3"
      :hoverEffect="true"
      hoverMode="grab"
      :clickEffect="true"
      clickMode="push"
      class="particles"
    >
    </vue-particles>
  </div>
</template>
<script>
import User from "../models/user";
// import Swal from "sweetalert2";

export default {
  name: "Login",
  data() {
    return {
      user: new User("", ""),
      loading: false,
      message: "",
    };
  },
  methods: {
    changePassword() {
      this.$store.dispatch("auth/changePassword", this.user);
    },
  },
  created() {
    this.user.id = this.$route.params.id;
  },
};
</script>
<style scoped>
.login-page {
  background-image: linear-gradient(
      to right top,
      rgb(13, 33, 60),
      rgb(52, 3, 62, 0.8)
    ),
    url("");
  min-height: 100%;
  background-size: cover;
  max-height: 100%;
  overflow-y: hidden;
}

.login-page .logo {
  margin-left: -40px;
}

.login-page .logo img {
  height: 100px;
  width: 170px;
  margin-top: -20px;
}

.login-page .logo h1 {
  display: block;
  margin-top: 60px;
}

.login-page .close {
  position: absolute;
  top: 40px;
  right: 40px;
  height: 30px;
  width: 30px;
  opacity: 1;
}

.login-container {
  width: 400px;
  height: 370px;
  margin-top: 40px;
  margin-left: calc(50% - 200px);
  margin-bottom: 20px;
  background: #fff;
  box-sizing: border-box;
  padding: 40px 20px;
  position: absolute;
}

.login-container img {
  width: 100px;
  height: 100px;
  position: absolute;
  left: calc(50% - 50px);
  border-radius: 50%;
  top: -50px;
}

.login-container h1 {
  text-align: center;
  font-size: 20px;
  margin-bottom: 20px;
}

.login-container label {
  display: block;
  text-align: left;
}

.login-container div {
  margin-bottom: 20px;
}

.login-container input[type="text"],
input[type="password"] {
  width: 100%;
  border: none;
  outline: none;
  border-bottom: 1px solid #000;
  background: transparent;
  color: #000;
  height: 40px;
}

.login-container input[type="submit"] {
  width: 100%;
  border: none;
  outline: none;
  height: 40px;
  background-color: #150485;
  color: #fff;
}
.login-container input[type="submit"]:hover {
  cursor: pointer;
  box-shadow: 1px 1px 10px #696969;
}

a {
  display: inline;
  text-decoration: none;
  font-size: 12px;
  margin: 0;
  padding: 0;
}

p {
  color: #000;
  font-size: 12px;
  margin: 0;
  padding: 0;
}
</style>
