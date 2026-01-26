<template>
  <div>
    <!-- Pass user data as props to ActiveUser component -->
    <!-- ":" is shorthand for "v-bind:" -->
    <active-user :username="user.name" :userage="user.age"></active-user>
    <!-- "@" is shorthand for "v-on:" (listens for custom events from child) -->
    <user-data @set-data="setUserData"></user-data>
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
  methods: {
    // Updates the user object with new name and age values
    setUserData(data) {
      this.user = {
        name: data.name,
        // "+": converts string to number (alternatives: Number(data.age), parseInt(data.age, 10))
        age: +data.age
      }
    }
  }
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
