<script setup>
import { ref, reactive, onMounted, watch } from "vue";

const tasks = ref([]);
const newTask = reactive({
  name: "",
  priority: "High",
});

onMounted(() => {
  const savedTasks = localStorage.getItem("tasks");
  if (savedTasks) {
    tasks.value = JSON.parse(savedTasks);
  }
});

watch(tasks, (newTasks) => {
  localStorage.setItem("tasks", JSON.stringify(newTasks));
}, { deep: true });

const addTask = () => {
  if (!newTask.name.trim()) {
    alert("Task name cannot be empty.");
    return;
  }
  tasks.value.push({ ...newTask });
  newTask.name = ""; 
  newTask.priority = "High"; 
};

const tasksByPriority = (priority) => {
  return tasks.value
    .filter(task => task.priority === priority)
    .sort((a, b) => a.name.localeCompare(b.name));
};
</script>

<template>
  <div class="app-container">
    <h1>Priority Task List</h1>

    <form @submit.prevent="addTask" class="task-form">
      <div class="inputDiv">
        <input 
        v-model="newTask.name" 
        type="text" 
        placeholder="Enter task name" 
        required
      />
      </div>
      <div class="selectDiv">
        <select v-model="newTask.priority">
        <option value="High">High</option>
        <option value="Medium">Medium</option>
        <option value="Low">Low</option>
      </select>
      </div>
      <div>
        <button type="submit">Add Task</button>
      </div>
    </form>

    <div v-for="priority in ['High', 'Medium', 'Low']" :key="priority" class="task-group">
      <h2>{{ priority }} Priority</h2>
      <ul>
        <li v-for="task in tasksByPriority(priority)" :key="task.name">
          {{ task.name }}
        </li>
      </ul>
      <p v-if="tasksByPriority(priority).length === 0">No tasks available in this category</p>
    </div>
  </div>
</template>

<style scoped>
.app-container {
  width: 800px;
  margin: 0 auto;
  background-color: gray;
  text-align: center;
}

.inputDiv{
  width: 600px;
  margin: 0 auto;
  
}
.selectDiv{
  width: 600px;
  margin: 0 auto;
  
}



h1 {
  text-align: center;
}


.task-form input,
.task-form select {
  padding: 10px;
  font-size: 1rem;
  border: 1px solid gray;
  margin-top:5px;
}
button{
  background: dodgerblue;
  padding: 0 5px;
  margin-top: 5px;
  
}

.task-group {
  margin-bottom: 20px;
  text-align: cener;
}

.task-group ul {
  list-style-type: none;
  padding: 0;
}

.task-group li {
  padding: 5px 0;
  border-bottom: 1px solid #ddd;
  
}
</style>