<template>
  <section class="mt-4">
    <input
      @keydown.enter="newItem"
      type="text"
      placeholder="Add Todo"
      class="w-full p-2 bg-gray-700 border-2 border-gray-400 rounded-md outline-none text-lg"
    />
  </section>
</template>

<script>
export default {
  props: {
    addTodo: Function,
  },

  setup(props) {
    const newItem = event => {
      props.addTodo(event.target.value);
      event.target.value = "";
    };

    return {
      newItem,
    };
  },
};
</script>
