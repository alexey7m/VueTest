<script setup>
import { ref, watchEffect } from "vue";

const obj = [
  {
    id: 11,
    name: "Jacket 1",
  },
  {
    id: 12,
    name: "Jacket 2",
  },
  {
    id: 13,
    name: "Jacket 3",
  },
  {
    id: 14,
    name: "Jacket 4",
  },
  {
    id: 15,
    name: "Hoodie 1",
  },
  {
    id: 16,
    name: "Hoodie 2",
  },
  {
    id: 17,
    name: "Hoodie 3",
  },
  {
    id: 18,
    name: "Hoodie 4",
  },
];

const selected = ref({});
const isActive = ref(false);

const addToSelect = (item) => {
  selected.value = item;
  isActive.value = true;
};
const removeItem = () => {
  isActive.value = false;
};
</script>

<template>
  <div>
    <div class="selectList _selected singleWrap">
      <div
        class="singleItem"
        :class="{ active: isActive }"
        @click="removeItem()"
      >
        <span v-if="isActive">{{ selected.name }}</span>
      </div>
    </div>
    <div class="selectList _select">
      <div class="item" v-for="item in obj" @click="addToSelect(item)">
        {{ item.name }}
      </div>
    </div>
  </div>
</template>
