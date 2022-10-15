<template>
  <main>
    <div class="df">
      <MultiSelector></MultiSelector>
      <SingleSelector></SingleSelector>
    </div>

    <!-- <MultiSelectItem :selected="selectedItems"> </MultiSelectItem> -->
  </main>
</template>
<style>
.df {
  display: flex;
  justify-content: space-between;
  max-width: 840px;
  min-width: 840px;
  margin: auto;
  border: 5px solid #000;
  padding: 15px;
  gap: 15px;
  min-height: 700px;
}
.df > * {
  display: flex;
  flex-direction: column;
  flex: 0 1 auto;
}
.selectList {
  display: flex;
  flex-wrap: wrap;
  border: 3px solid #000;
  margin-top: 15px;
  gap: 10px;
  padding: 10px;
}
.item {
  display: flex;
  width: calc(25% - 8px);
  justify-content: center;
  align-items: center;
  height: 50px;
  border: 1px solid #000;

  cursor: pointer;
}
._select {
  width: 100%;
  height: 100%;
  flex: 1 1 auto;
  align-content: flex-start;
  position: relative;
}
._selected {
  flex: 0 1 180px;
  margin-top: 0;
}
.count {
  position: absolute;
  right: 15px;
  bottom: 5px;
}
.singleWrap {
  justify-content: flex-end;
}
.singleItem {
  height: 100%;
  width: 100px;
  border: 1px solid #000;
  display: flex;
  justify-content: center;
  align-items: center;
  display: none;
  cursor: pointer;
}
.singleItem.active {
  display: flex;
}
</style>

<script setup>
//import { ref, watchEffect } from "vue";
//import MultiSelectItem from "../components/MultiSelectItem.vue";
import MultiSelector from "../components/MultiSelector.vue";
import SingleSelector from "../components/SingleSelector.vue";

/*const selectedItems = ref([]);
const update = (selected) => {
  selectedItems.value = selected;
};
watchEffect(() => {
  console.log(selectedItems);
});*/
//const emit = defineEmits(["getSelected"]);
</script>
