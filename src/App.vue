<template>
  <div>
    <!-- Pass user data as props to ActiveUser component -->
    <!-- ":" is shorthand for "v-bind:" -->
    <active-user :username="user.name" :userage="user.age"></active-user>
    <user-data></user-data>
  </div>
</template>

<script>
export default {
  data() {
    return {
      user: {
        name: 'Rikuto Mikado',
        age: 18
      }
    };
  },

};
</script>

<style>
html {
  font-family: sans-serif;
}

section {
    margin: 2rem auto;
    max-width: 40rem;
    border-radius: 12px;
    border: 1px solid #ccc;
    padding: 1rem;
}
</style>
