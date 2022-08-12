<template>
  <div class="todoItems">
    <div class="todo-item" v-bind:class="{ 'is-complete': todo.completed }">
      <p>
        <input type="checkbox" v-on:change="markComplete" />
        {{ todo.title }}
      </p>
      <span @click="$emit('del-todo', todo.id)">
        <i class="fa fa-trash pointer"></i>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["todo"],
  methods: {
    markComplete() {
      // eslint-disable-next-line vue/no-mutating-props
      this.todo.completed = !this.todo.completed;
    },
  },
};
</script>

<style scoped>
.todoItems {
  display: flex;
  min-width: 100vw;
  justify-content: center;
}
.todo-item {
  width: 600px;
  background: #f4f4f4;
  padding: 10px;
  border-bottom: 1px solid #ccc;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.is-complete {
  text-decoration: line-through;
  color: #ff8800;
}

p {
  display: inline;
}

.fa-trash:hover {
  color: #ff4444;
  cursor: pointer;
}

span {
  right: 0;
}
</style>
