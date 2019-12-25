<template>
  <div class="about">
    <h1>代办事项</h1>
    <TodoList></TodoList>
  </div>
</template>
<script>
import TodoList from "@/components/TodoList"
export default {
  name: "About",
  components: {
    TodoList
  }
}
</script>