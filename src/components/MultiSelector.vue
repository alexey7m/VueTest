<script setup>
import { ref, watchEffect } from "vue";

const obj = [
  {
    id: 1,
    name: "Shoes 1",
  },
  {
    id: 2,
    name: "Shoes 2",
  },
  {
    id: 3,
    name: "Shoes 3",
  },
  {
    id: 4,
    name: "Shoes 4",
  },
  {
    id: 5,
    name: "T-shirt 1",
  },
  {
    id: 6,
    name: "T-shirt 2",
  },
  {
    id: 7,
    name: "T-shirt 3",
  },
  {
    id: 8,
    name: "T-shirt 4",
  },
];

const selected = ref([]);
const addToSelect = (item) => {
  if (selected.value.find((i) => i.id == item.id)) return;
  if (selected.value.length > 5) {
    selected.value[0] = item;
  } else {
    selected.value.push(item);
  }
};
const removeItem = (item) => {
  let index = selected.value.indexOf(item);
  selected.value.splice(index, 1);
};
</script>

<template>
  <div>
    <div class="selectList _selected">
      <div class="item" v-for="item in selected" @click="removeItem(item)">
        {{ item.name }}
      </div>
      <div class="count">Selected: {{ selected.length }} / 6</div>
    </div>
    <div class="selectList _select">
      <div class="item" v-for="item in obj" @click="addToSelect(item)">
        {{ item.name }}
      </div>
    </div>
  </div>
</template>
