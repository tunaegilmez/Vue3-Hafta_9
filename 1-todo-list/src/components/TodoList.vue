<template>
  <section class="mt-4">
    <TodoListItem
      @delete-event="$emit('delete-event', $event)"
      v-for="todoItem in todoList"
      :key="todoItem.id"
      :todo="todoItem"
    />
    <small>{{ todoLength }} Adet Todo Var</small>
    <Summary :todoList="todoList" />
  </section>
</template>

<script>
import { computed } from "vue";
import TodoListItem from "./TodoListItem.vue";
import Summary from "./Summary.vue";

export default {
  components: { TodoListItem, Summary },
  props: {
    todoList: Array,
  },
  setup(props) {
    const todoLength = computed(() => props.todoList.length);
    return { todoLength };
  },
};
</script>
