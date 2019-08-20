<template>
  <div id="employee-form">
    <form @submit.prevent="handleSubmit">
      <label>Employee name</label>
      <input v-model="employee.name" type="text" />
      <label>Employee Email</label>
      <input v-model="employee.email" type="text" />
      <button type="submit">Add Employee</button>
    </form>
  </div>
</template>

<script>
  export default {
  name: 'employee-form',
  data() {
    return {
        employee: {
            name: '',
            email: '',
        },
    }  
  },
  methods: {
    handleSubmit() {
        this.$emit('add:employee', this.employee)
        this.employee.name = ''
        this.employee.email = ''
    },
  },
}
</script>

<style scoped>
  form {
    margin-bottom: 2rem;
  }
</style>