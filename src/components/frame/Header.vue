<template>
  <div id="Header">
    <b-navbar fixed="top" toggleable="lg" type="dark" style="background-color:rgba(177, 179, 179,0.8)">
      <img id="logo" src="/logo.png">
      <b-navbar-brand class="text-xl font-weight-bold" href="#" id="title">Ms.SweetBakes</b-navbar-brand>

      <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav class="ml-auto">
          <b-nav-item class ="font-weight-bold" v-on:click="redirect('/register')" v-if="auth.user === null">Sign Up</b-nav-item>
          <b-nav-item class ="font-weight-bold" v-on:click="redirect('/login')" v-if="auth.user === null">Login</b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<style scoped lang="scss">
@import "~assets/colors.scss";
#title {
  color: #E3CD81FF !important;
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen,
    Ubuntu, Cantarell, "Open Sans", "Helvetica Neue", sans-serif;
  padding-left: 10px;
}
#logo {
  height: 40px;
}

.navbar-dark .navbar-nav .nav-link {
  color: #E3CD81FF !important;
}

</style>

<script>
import ROUTER from "router";
import AUTH from "services/auth";
export default {
  data() {
    return {
      auth: AUTH
    };
  },
  methods: {
    redirect(route) {
      ROUTER.push(route);
    }
  }
};
</script>



