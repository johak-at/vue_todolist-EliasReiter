<script setup>
import { ref } from 'vue';
const list = ref([]);
const newItem = ref('');

function addItem() {
    list.value.push(newItem.value);
    newItem.value = '';

}


</script>


<!-- create a todolist with vue -->
<template>
    <div>
        <h1>Todo List</h1>
        <input type="text" v-model="newItem" />
        <button @click="addItem">Add</button>
        <ul>
            <li v-for="item in list" :key="item">{{ item }}</li>
        </ul>
    </div>

    <!--delete item from todolist-->
    <button @click="deleteItem">Delete</button>
</template>

