<script setup>
const list = [1, 2, 3, 4, 5];

const tasks = [
  {id:1, title:"Complete porject proposal", status:"In Process"},
  {id:2, title:"update website content", status:"Completed"},
  {id:3, title:"Fix bug in user autherntication", status:"In Progress"},
  {id:4, title:"prepare presentation slide", status:"Pending"},
  {id:5, title:"Test new feature implementation", status:"In Progress"},
  {id:6, title:"sdfsdjflsdjfsd", status:"Pending"},
  {id:7, title:"sdfsdj flsdj fsd", status:"Completed"},
];

function getCompletedTasks(){
  return tasks.filter(task=>"Completed"==task.status);
}
function getTasksInProgress(){
  return tasks.filter(task=>"In Progress"==task.status);
}
function getTasksPending(){
  return tasks.filter(task=>"Pending"==task.status);
}
</script>

<template>
  <section class="container max-auto">
    <section
      class="container max-auto bg-gray-400 m-auto justify-center w-11/12"
    >
    <h1>Completed Tasks</h1>
      <div class="ml-10" v-for="(task, index) in getCompletedTasks()" :key="index">
        {{ task.id }}. {{ task.title }}
      </div>
      <hr>
      <h1>In Progress tasks</h1>
       <div class="ml-10" v-for="(task, index) in getTasksInProgress()" :key="index">
        {{ task.id }}. {{ task.title }}
      </div>
      <h1>Pending tasks</h1>
       <div class="ml-10" v-for="(task, index) in getTasksPending()" :key="index">
        {{ task.id }}. {{ task.title }}
      </div>
    </section>
  </section>
</template>

<style scoped></style>
