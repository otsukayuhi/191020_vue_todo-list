<template>
  <div class="template-inner">
    <div class="inputArea">
      <input
        class="inputArea_inputform"
        placeholder="Enter activity…"
        type="text"
      />
      <button class="inputArea_inputbtn">
        <img src="@/assets/add@2x.png" alt="">
      </button>
    </div>

    <ul class="todoList">
      <li class="todoList_item" v-for="todoList in todoLists" :key="todoList.id">
        <button class="todoList_check">
          <img src="@/assets/success_check.png" v-if="todoList.checked" alt="">
          <img src="@/assets/success@2x.png" v-else alt="">
        </button>
        <p class="todoList_txt">{{todoList.text}}</p>
        <button class="todoList_delete">
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
          todoLists:[
              {
                  id:0,
                  text:"hoge",
                  checked:true
              },
              {
                  id:1,
                  text:"huga",
                  checked:false
              }
          ]
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
