<script setup lang="ts">
const { data: session } = await useFetch('/api/auth/session', {
  headers: useRequestHeaders(),
});
const update = () => {
  window.location.reload();
};
const login = async () => $fetch('/api/auth/login').then(() => update());
const logout = async () => $fetch('/api/auth/logout').then(() => update());
</script>

<template>
  <div>
    <button @click="login">Login</button>
    <button @click="logout">Logout</button>
    <br /><br />
    {{ session }}
  </div>
</template>
