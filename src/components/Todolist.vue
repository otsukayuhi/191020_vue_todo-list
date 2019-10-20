<template>
  <div class="template-inner">
    <div class="inputArea">
      <input class="inputArea_input" type="text" />
      <button>btn</button>
    </div>

    <ul class="todoList">
      <li class="todoList_item">Do loundry</li>
      <li class="todoList_item">Clean kithen</li>
      <li class="todoList_item">Cook dinner</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "TodoList"
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.template-inner {
  padding: 40px 20px;
}

.inputArea {
  width: 100%;
  height: 56px;
  border-radius: 10px;
  background-color: #4bc9d0;
}

.inputArea_input {
  background-color: transparent;
  padding: 20px;
}

.todoList {
}

.todoList_item {
}
</style>
