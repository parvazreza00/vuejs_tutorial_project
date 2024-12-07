
<script setup>
const list = [1, 2, 3, 4, 5, 6, 7];

const evenNumbers = list.filter(num=> num % 2 === 0 );
const oddNumbers = list.filter(num=> num %2 !=0);

const words = ["apple","banana","grape","kiwi", 'watermelon'];

const longwords = words.filter(word => word.length > 5);

const users = [
  {id: 1, name:"Alce", active:true},
  {id: 2, name:"Malek", active:false},
  {id: 3, name:"Kalek", active:false},
  {id: 4, name:"Tomal", active:true},
  {id: 5, name:"Hasan", active:true},
];

const activeUsers = users.filter(user => user.active);
const inActiveUsers = users.filter(user => !user.active);

const numbers = [10,20, 30, 40, 50];
const filtered = numbers.filter((num, index)=> index % 2 === 0);

const products = [
  {name:'Laptop', price:1500, available: true},
  {name:'Phone', price:1000, available: false},
  {name:'Tablet', price:1200, available: true},
  {name:'Desktop', price:1100, available: true},
];

const affordableAvailabelProducts = products.filter(product => product.price < 1200 && product.available);





</script>

<template>
  <section class="container max-auto">
    <section
      class="container max-auto bg-gray-400 m-auto justify-center w-11/12"
    >
    <h1>JS filter() method:</h1>
    <h1>Even Numbers:</h1>
      <div class="ml-10" v-for="(item, index) in evenNumbers" :key="index">
         {{ item }}
      </div>
      <hr>
    <h1>Odd Numbers:</h1>
      <div class="ml-10" v-for="(item, index) in oddNumbers" :key="index">
         {{ item }}
      </div>
      <hr>
    <h1>Longest words greater than 5 characters:</h1>
      <div class="ml-10" v-for="(item, index) in longwords" :key="index">
        {{ index }} - {{ item }}
      </div>
      <hr>
    <h1>Active Users:</h1>
      <div class="ml-10" v-for="(item, index) in activeUsers" :key="index">
        {{ item.id }} - {{ item.name }}
      </div>
      <hr>
    <h1>InActive Users:</h1>
      <div class="ml-10" v-for="(item, index) in inActiveUsers" :key="index">
        {{ item.id }} - {{ item.name }}
      </div>
     <hr>
    <h1>Filter Even number with indexes:</h1>
      <div class="ml-10" v-for="(item, index) in filtered" :key="index">
        {{ index }} - {{ item }}
      </div>
     <hr>
    <h1>Available Products:</h1>
      <div class="ml-10" v-for="(item, index) in affordableAvailabelProducts" :key="index">
        {{ index + 1 }}.  {{ item.name }} - {{ item.price }}
      </div>
     
    
    </section>
  </section>
</template>

<style scoped></style>
