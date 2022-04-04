<template>
  <div class="todo-list">
    <strong> <input type="checkbox" /> </strong> {{ todo }}
    <div style="float: right">
      <span class="fa fa-edit text-primary" @click="$emit('update', todo)"></span> &nbsp;
      <span class="fa fa-remove text-danger" @click="$emit('remove', todo)"></span>
    </div>
  </div>
</template>

<script>
export default {
  name: "view",
  props: {
    todo: String,
    index: Number,
  },
  emits: ["remove"],
};
</script>

<style scoped>
.todo-list {
  padding: 10px;
  text-transform: capitalize;
  text-align: left;
}
</style>
