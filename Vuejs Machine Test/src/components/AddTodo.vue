<template>
    <div class="container">
        <br>
        <h1 class="text-center">Todos App</h1>
        <br><br>
        <form @submit="addTodo">
        <div class="form-group">
            <input required type="text" v-model="email" placeholder="email" name="email" id="" class="form-control">
        </div>
        <div class="form-group">
            <input required type="text" v-model="first_name" placeholder=" first_name" name=" first_Name" id="" class="form-control">
        </div>
        <div class="form-group">
            <input required type="text" v-model="Last_name" placeholder="Last_name" name="Last_Name" id="" class="form-control">
        </div>
        <div class="form-group">
            <button class="btn btn-block btn-danger">
                Add Todo
            </button>
        </div>
        </form>
    </div>
</template>
<script>

export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    addTodo(e) {
        e.preventDefault()
      const newTodo = {
        id:Date.now(),
        email: this.email,
        first_name: this. first_name,
        Last_name: this. Last_name,
        
        completed: false
      }
      // Send up to parent
      this.$emit('add-todo', newTodo);

      this.title = '';
    }
  }
}
</script>

<style scoped>

</style>