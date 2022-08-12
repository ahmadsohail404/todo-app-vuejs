<template>
  <div class="inputEl">
    <input
      v-model="title"
      type="text"
      placeholder="Enter a Todo"
      class="form-control"
      @keyup.enter="addTodo"
    />
    <button
      @click="addTodo"
      class="btn btn-primary rounded-0"
      ref="changeOnEdit"
    >
      Add
    </button>
  </div>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      title: "",
    };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        title: this.title,
        completed: false,
      };
      if (this.title.length === 0) {
        this.$vToastify.error("Blank todo!");
        return;
      }
      //send up to parent
      this.$emit("add-todo", newTodo);
      this.title = "";
    },
  },
};
</script>

<style scoped>
.inputEl {
  display: flex;
  justify-content: center;
  padding: 3rem;
}

input {
  width: 32rem;
}
form {
  display: flex;
}
input::placeholder {
  color: #4285f4;
}
</style>
