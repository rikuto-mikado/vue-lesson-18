<template>
  <section>
    <form @submit.prevent="submitData">
      <!-- v-model: two-way binding (syncs input value with enteredName) -->
      <input type="text" placeholder="Name" v-model="enteredName" />
      <input type="text" placeholder="Age" v-model="enteredAge" />
      <button>Set User Data</button>
    </form>
  </section>
</template>

<script>
export default {
  // emits: declares custom events this component can emit to parent
  emits: ['set-data'],
  data() {
    return {
      enteredName: '',
      enteredAge: ''
    }
  },
  methods: {
    submitData() {
      // $emit: sends custom event 'userdata' with payload to parent component    
      this.$emit('set-data', {
        name: this.enteredName,
        age: this.enteredAge
      })
    }
  }
};
</script>
