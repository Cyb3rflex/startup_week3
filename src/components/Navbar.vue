<template>
  <nav class="navbar">
    <div class="logo px-4 py-4">Eventful Moments</div>
    <div class="menu">
      <router-link to="/" exact-active-class="active">Login</router-link>
      <router-link to="/register" exact-active-class="active"
        >Register</router-link
      >
    </div>
  </nav>
</template>

<style scoped>
.navbar {
  background: teal;
  padding: 15px;
  color: white;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.menu a {
  margin-right: 15px;
  text-decoration: none;
  color: white;
}

.menu a:hover,
.menu a.active {
  text-decoration: underline;
}
</style>
