<template>
 <div class="home">
 <img alt="Vue logo" src="../assets/logo.png" />
 <br><br>
 <home />
 </div>
</template>
<script>
// @ is an alias to /src
import home from "@/components/Home.vue";
export default {
 name: "Home",
 components: {
 home
 }
};
</script>