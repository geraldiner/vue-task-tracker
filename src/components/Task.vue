<template>
  <div
    @dblclick="$emit('toggle-reminder', task.id)"
    :class="[task.reminder ? 'reminder' : '', 'task']"
  >
    <div class="details">
      <h3>{{ task.text }}</h3>
      <p>{{ task.day }}</p>
    </div>
    <div class="icons">
      <i @click="$emit('delete-task', task.id)" class="fas fa-times delete"></i>
    </div>
  </div>
</template>

<script>
import AddTask from "./AddTask";

export default {
  name: "Task",
  components: {
    AddTask,
  },
  props: {
    task: Object,
  },
  data() {
    return {
      text: "",
      day: "",
      reminder: false,
    };
  },
};
</script>

<style scoped>
.delete {
  color: red;
}

.edit {
  color: blue;
}
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
  display: flex;
  justify-content: space-between;
}
.task.reminder {
  border-left: 5px solid green;
}

.icons {
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}

.add-form {
  margin-bottom: 40px;
}
.form-control {
  margin: 20px 0;
}
.form-control label {
  display: block;
}
.form-control input {
  width: 100%;
  height: 40px;
  margin: 5px;
  padding: 3px 7px;
  font-size: 17px;
}
.form-control-check {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.form-control-check label {
  flex: 1;
}
.form-control-check input {
  flex: 2;
  height: 20px;
}
</style>