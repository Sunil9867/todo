<template>
  <div class="container">
    <div class="text-center">
      <Header />

      <!-- <h1>Todo :</h1> -->
      <div v-for="(todo, index) in todo_list" v-bind:key="index">
        <View :todo="todo" :index="index" @remove="remove" @update="update" />
      </div>

      <CustomInput @addValueToList="add" :msg="msg" />
    </div>
  </div>
</template>

<script>
import CustomInput from "./CustomInput.vue";
import View from "./view.vue";
import Header from "./Header.vue";

export default {
  name: "Todo",
  components: {
    CustomInput,
    View,
    Header,
  },
  data() {
    return {
      todo_list: ["go to school.", "call with doctor", "Jak birthday today", "Sleeping"],
      msg: "",
    };
  },
  methods: {
    add(value) {
      //   debugger;
      if (value !== "") {
        this.todo_list.push(value);
        this.msg = "";
        console.log(this.msg);
      } else {
        alert("Write something ....");
      }
    },
    remove(value) {
      console.log(value);
      this.todo_list = this.todo_list.filter(function (todo) {
        return todo !== value;
      });
    },
    update(value) {
      console.log(value);
      this.msg = value;
      this.remove(value);
    },
  },
};
</script>

<style scoped></style>
