<script setup>

import AppHeader from'./components/AppHeader.vue'


import { ref } from "vue";

const lists = ref([]);
const str = ref("");

const add = () => {
  lists.value.push(str.value);
  str.value = ""
};

const remove =(param) =>{
  lists.value.splice(param,1)
}
</script>

<template>

  <AppHeader color="blue">props </AppHeader>

  <input type="text" size="30" v-model="str" />
  <p>
    <button @:click="add()">追加</button>
  </p>

  <p>
    <ul v-if="lists.length > 0">
      <li v-for="(list ,i) in lists" :key="i">{{list}} <span @:click="remove(i)" style="cursor: pointer;">x</span></li>
       
    </ul>
    </p>
  </template>
