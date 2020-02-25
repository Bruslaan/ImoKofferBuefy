<template>
  <div>
    <b-navbar fixed-top>
      <template slot="brand">
        <b-navbar-item tag="router-link" :to="{ path: '/' }">
          <img
            src="https://dienstleister.internetworld.de/static/b5b0af60efe359c3fd27dc1fe2d0a62d/adf82/placeholder.png"
            alt="Lightweight UI components for Vue.js based on Bulma"
          />
        </b-navbar-item>
      </template>
      <template slot="start">
        <b-navbar-item href="#">Home</b-navbar-item>
        <b-navbar-item href="#">Documentation</b-navbar-item>
      </template>
    </b-navbar>

    <section class="main-content">
      <div class>
        <nuxt />
      </div>
    </section>
  </div>
</template>

<script>
export default {
  components: {},
  data() {
    return {};
  }
};
</script>

<style>
.center{
  text-align: center;
}
.sticky {
  position: -webkit-sticky;
  position: sticky;
  bottom: 0;
  background-color: white;
 text-align: center;
  padding: 10px;
  padding-bottom: 30px;
  font-size: 20px;
  z-index: 99;
}
</style>
