<template>
  <div id="app">
    <AppHeader />
    <div class="container mt-3">
      <router-view />
    </div>
  </div>
</template>
<script>
import AppHeader from "@/components/AppHeader.vue";
export default {
  components: {
    AppHeader,
  },
  data() {
    return {
      component: "Login",
    };
  },
  methods: {
    loginF() {
      this.component = "Login";
    },
    RegisterF() {
      this.component = "Register";
    },
  },
};
</script>

<style>
.page {
  max-width: 400px;
  margin: auto;
}
nav {
  display: none;
}
</style>
