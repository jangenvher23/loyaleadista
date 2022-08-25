<template>
  <v-app>
    <Nav />
    <v-main class="main_content">
      <Login />
    </v-main>
  </v-app>
</template>

<script>
import Nav from "~/components/Nav.vue";
import Login from "./login/index.vue";

export default { components: { Nav, Login } };
</script>

<style>
.main_content {
  background-color: #fff;
}
</style>
