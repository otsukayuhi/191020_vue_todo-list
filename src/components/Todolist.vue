<template>
  <div class="template-inner">
    <div class="inputArea">
      <input
        class="inputArea_inputform"
        placeholder="Enter activity…"
        type="text"
        v-model="inputText"
      />
      <button class="inputArea_inputbtn" @click="addTodoList">
        <img src="@/assets/add@2x.png" alt="" />
      </button>
    </div>

    <ul class="todoList">
      <li
        class="todoList_item"
        v-for="todoList in todoLists"
        :key="todoList.id"
        v-bind:class="{ '-checked': todoList.checked }"
      >
        <button class="todoList_check" @click="check(todoList.id)">
          <img
            src="@/assets/success_check.png"
            v-if="todoList.checked"
            alt=""
          />
          <img src="@/assets/success@2x.png" v-else alt="" />
        </button>
        <p class="todoList_txt">{{ todoList.text }}</p>
        <button class="todoList_delete" @click="remove(todoList.id)">
          <img src="@/assets/delete@2x.png" alt="ゴミ" />
        </button>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  data: () => {
    return {
      inputText: "",
      todoLists: []
    };
  },
  methods: {
    addTodoList() {
      const inputText = this.inputText;
      const time = new Date();
      const todo = {
        id: time.getTime(),
        text: inputText,
        checked: false
      };
      this.todoLists.unshift(todo);
      this.inputText = "";
    },
    check(id) {
      const todolists = this.todoLists;
      const targetTodo = todolists.find(item => {
        return item.id === id;
      });
      targetTodo.checked = !targetTodo.checked;
    },
    remove(id) {
      const todolists = this.todoLists;
      const index = todolists.findIndex(item => {
        return item.id === id;
      });
      todolists.splice(index, 1);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.template-inner {
  padding: 40px 20px;
}

.inputArea {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  /*height: 56px;*/
  border-radius: 10px;
  background-color: #4bc9d0;
  padding: 10px 20px;
}

.inputArea_inputform {
  flex: 1;
  margin-right: 10px;
  padding: 10px 0;
  background-color: transparent;
  font-size: 15px;
  color: #ffffff;
  /*background: red;*/
}

.inputArea_inputform::placeholder {
  color: #ffffff;
}

.inputArea_inputbtn {
  width: 28px;
  height: 28px;
  background: tomato;
  /*object-fit: contain;*/
}

.todoList {
}

.todoList_item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 16px 14px;
  // &.-checked{
  //   display: none;

  // }
}

.todoList_check {
  width: 24px;
  height: 24px;

  .todoList_item.-checked & {
  }
}

.todoList_txt {
  flex: 1;
  padding: 0 20px;
  font-size: 15px;
  .todoList_item.-checked & {
    color: #9b9b9b;
    text-decoration: line-through;
  }
}

.todoList_delete {
  width: 15px;
  height: 19.4px;
  // background: url('delete@2x.png') center no-repeat;
}
</style>
