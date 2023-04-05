<template>
  <nav class="navbar navbar-expand navbar-dark bg-dark">
    <a href="/" class="navbar-brand">Ứng dụng Quản lý danh bạ</a>
    <div class="mr-auto navbar-nav">
      <li class="nav-item">
        <router-link :to="{ name: 'contactbook' }" class="nav-link">
          Danh bạ
          <i class="fas fa-address-book"></i>
        </router-link>
      </li>
      <li class="nav-item" v-if="!isChecked">
        <router-link :to="{ name: 'Login' }" class="nav-link">
          Đăng nhập
          <i class="fas fa-address-book"></i>
        </router-link>
      </li>
      <li class="nav-item" v-else>
        <router-link :to="{ name: 'Logout' }" class="nav-link">
          Đăng xuất
          <i class="fas fa-address-book"></i>
        </router-link>
      </li>
    </div>
  </nav>
</template>
<script>
import { ref } from "vue";
export default {
  setup() {
    const isChecked = ref(false);
    if (localStorage.getItem("token") == null) {
      //Nguoi dung chua dang nhap
      isChecked.value = false;
    } else {
      // login roi
      isChecked.value = true;
    }
    return {
      isChecked,
    };
  },
};
</script>
