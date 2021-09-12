<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task bg-light m-1 py-2 px-4']"
  >
    <h3 class="d-flex align-items-center justify-content-between">
      {{ task.text }}
      <i
        @click="$emit('delete-task', task.id)"
        class="fas fa-times text-danger"
      ></i>
    </h3>
    <p>{{ task.day }}</p>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: Object,
  },
};
</script>

<style scoped>
.task.reminder {
  border-left: 5px solid green;
}
</style>
