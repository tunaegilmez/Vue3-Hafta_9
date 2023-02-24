<template>
  <div class="flex justify-between items-center odd:bg-gray-600 rounded-md p-4">
    <label :for="`todo_${todo.id}_completed`">
      <input
        v-model="todo.completed"
        type="checkbox"
        :id="`todo_${todo.id}_completed`"
        class="mr-2"
      />
      <span class="text-lg ml-3"> {{ todo.title }} </span>
    </label>
    <button
      @click="deleteItem"
      class="px-5 py-1 rounded-md bg-red-400 active:bg-red-400 hover:bg-red-500"
    >
      Sil
    </button>
  </div>
</template>

<script>
export default {
  props: {
    todo: Object,
  },
  setup(props, { emit }) {
    const deleteItem = () => {
      emit("delete-event", props.todo);
    };
    return {
      deleteItem,
    };
  },
};
</script>
