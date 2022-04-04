<template>
  <fieldset>
    <form @submit.prevent="$emit('addValueToList', msg)">
      <div class="input-group mb-3">
        <input
          type="text"
          v-model="msg"
          name=""
          class="form-control"
          placeholder="Enter Something...."
          required
        />
        <div class="input-group-append">
          <button type="submit" name="" class="btn btn-primary">
            <span class="fa fa-plus"></span>
          </button>
        </div>
      </div>
    </form>
  </fieldset>
</template>

<script>
export default {
  name: "CustomInput",
  props: {
    msg: String,
  },
  emits: ["addValueToList"],
  data() {
    return {};
  },
};
</script>

<style scoped>
.btn {
  /* border-radius: 50%; */
  /* border: 1px solid black; */
  /* background-color: orange; */
  /* color: white; */
  /* position: relative;
  left: 50%;
  transform: translateY(50%); */
}
.outerDiv {
  width: 100%;
  text-align: center;
}
</style>
