<template>
  <main class="todo-wrap">
    <div class="todo-wrap-text">
      <label for="text">请输入代办</label>
      <input type="text" v-model="todoValue" name="text" id="text" />
      <button @click="handleAdd" class="primary-color">添加</button>
    </div>
    <div v-for="(item, index) in todoList" :key="index" class="todo-wrap-list">
      <div>
        <span>{{item.text}}</span>
        <button @click="handleDelete(index)" class="danger-color delete">删除</button>
      </div>
    </div>
  </main>
</template>
<script>
export default {
  name: "TodoList",
  data() {
    return {
      todoValue: "",
      todoList: [],
      index: 0
    }
  },
  methods: {
    
    handleAdd() {
      if (this.todoValue === "") return
      this.todoList.push({ text: this.todoValue, done: false })
      this.todoValue = ""
    },
    // 删除？
    handleDelete(index) {
      this.todoList.splice(index, 1)
    }
  }
}
</script>

<style lang="scss">
.primary-color {
  color: #fff;
  background-color: #409eff;
  border-color: #409eff;
}
.primary-color:focus,
.primary-color:hover {
  background: #66b1ff;
  border-color: #66b1ff;
  color: #fff;
}
.danger-color {
  color: #fff;
  background-color: #f56c6c;
  border-color: #f56c6c;
}
.danger-color:focus,
.danger-color:hover {
  background: #f78989;
  border-color: #f78989;
  color: #fff;
}
.todo-wrap {
  width: 400px;
  height: auto;
  margin: 100px auto;
  &-text,
  &-list {
    display: flex;
    & .delete {
      align-items: flex-end;
    }
  }
}
.todo-wrap-list {
  margin-top: 10px;
  width: 252px;
}
</style>
