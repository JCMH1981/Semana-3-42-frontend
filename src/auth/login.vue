<template>
 <div class="container">
 <div class="row">
 <div class="col-lg-6 offset-lg-3 col-sm-10 offset-sm-1">
 <form
 class="text-center border border-success p-5"
 style="margin-top:70px;height:auto;padding-top:100px !important;"
 @submit.prevent="loginUser"
 >
 <h1 class="h3 mb-3 font-weight-normal" style="textalign: center"> Iniciar sesión</h1>
 <input
 type="text"
 id="email"
 class="form-control mb-5"
 placeholder="Email"
 v-model="login.email"
 />
 <!-- Password -->
 <input
 type="password"
 id="password"
 class="form-control mb-5"
 placeholder="Contraseña"
 v-model="login.password"
 />
 <!-- inicio sesion button -->
 <center>
 <button class="btn btn-success btn-block w-75 my4" type="submit">
 Inicio de sesion
 </button>
 </center>
 </form>
 </div>
 </div>
 </div>
</template>
<script>
import swal from "sweetalert";
export default {
 data() {
 return {
 login: {
 email: "",
 password: ""
 }
 };
 },
 methods: {
 async loginUser() {
 try {
 let response = await this.$http.post("/api/auth/signin", this.login);
 console.log(response.data);
 let token = response.data.accessToken;
 localStorage.setItem("jwt", token);
 if (token) {
 swal("Exitoso", "login exitoso", "success");
 this.$router.push("/home");
 }
 } catch (err) {
 swal("Error", "datos incorrectos", "error");
 console.log(err.response);
 }
 }
 }
};
</script>