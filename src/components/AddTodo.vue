<template>
  <div class="new">
    <input
      type="text"
      id="new-todo"
      placeholder="to do something"
      v-model="newTodoInput"
      v-on:keydown.enter="addTodo(newTodoInput)"
    />
    <button class="add-new-btn" @click="addTodo(newTodoInput)">Add</button>
  </div>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return {
      newTodoInput: "",
    };
  },
  methods: {
    addTodo(newTodo) {
      console.log("newTodo", newTodo);
      this.$store.commit("addTodo", newTodo);
      console.log("before newTodoInput", this.newTodoInput);

      //to reset input field to empty
      this.newTodoInput = "";
      console.log("after newTodoInput", this.newTodoInput);
    },
  },
};
</script>

<style scoped>
.new {
  width: 100%;
  font-size: 18px;
}

#new-todo {
  padding: 12px 16px;
  line-height: 1;
  outline: none;
}

.add-new-btn {
  padding: 12px 16px;
  border: 1px solid #dadadc;
  background-color: #efefef;
  cursor: pointer;
}
</style>
