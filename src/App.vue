<template>
 <div id="app">
     
      <router-link to="/home">Home</router-link> |
      <router-link to="/about">Services</router-link> |
      <router-link to="/team">Team</router-link> |
      <router-link to="/news">News</router-link> |
      <router-link to="/contactus">Contact Us</router-link> 
     <div id="nav">
      
      
    </div> 
 <router-view />
 </div>
</template>
<style>
#app {
 font-family: Avenir, Helvetica, Arial, sans-serif;
 -webkit-font-smoothing: antialiased;
 -moz-osx-font-smoothing: grayscale;
 text-align: center;
 color: #2c3e50;
}
#nav {
 padding: 30px;
}
#nav a {
 font-weight: bold;
 color: #2c3e50;
}
#nav a.router-link-exact-active {
 color: #42b983;
}
</style>
