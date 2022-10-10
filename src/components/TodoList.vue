<script setup>
import { computed } from "@vue/reactivity";
import { ref } from "vue";
const list = ref([]);
const newItem = ref("");

const filteredList = computed(() => {
  let result = [];
  for (let i = 0; i < list.value.length; i++) {
    if (list.value[i].toLowerCase().includes(filter.value.toLowerCase())) {
      result.push(list.value[i]);
    }
  }
});

function addItem() {
  list.value.push(newItem.value);
  newItem.value = "";
}


function deleteItem(index) {
  list.value.splice(index, 1);

}
</script>


<!--create a todolist with vue-->
<template>
  <div>
    <h1>Todo List</h1>
    <input @keyup.enter="additem" type="text" v-model="newItem" />
    <!--<input @keyup.enter="filteritem" type="text" v-model="filteritem" />-->
    <button @click="addItem">Add</button>
    <input type="text" placeholder="filter List" v-model="filter">
    <ul>
      <li v-for=" (item ,index) in list" :key="item">{{ index }} - {{item}}

        <button @click="deleteItem(item)">Delete</button>
      </li>
    </ul>

  </div>



</template>







