<template>
  <div :class="task.state" class="list-item">
    <label class="checkbox">
      <input :checked="isChecked" disabled name="checked" type="checkbox" />
      <span class="checkbox-custom" @click="$emit('archive-task', task.id)" />
    </label>
    <div class="title">
      <input
        :value="task.title"
        placeholder="Input title"
        readonly
        type="text"
        style="background: red;"
      />
    </div>

    <div class="actions">
      <a v-if="!isChecked" @click="$emit('pin-task', task.id)">
        <span class="icon-star" />
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "Task",
  props: {
    task: {
      type: Object,
      required: true,
      default: () => ({ id: "", state: "", title: "" }),
      validator: task => ["id", "state", "title"].every(key => key in task)
    }
  },
  computed: {
    isChecked() {
      return this.task.state === "TASK_ARCHIVED";
    }
  }
};
</script>
