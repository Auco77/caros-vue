<script setup>
import { ref } from 'vue';

const text = ref('Edit me');
const checked = ref(true);

const checkedNames = ref([]);
const names = ['Jack', 'Bira', 'Auco', 'Batman', 'Victoria', 'Akuma', 'Oni'];

const picked = ref('');
// const selected = ref('A');
// const multiSelected = ref(['A']);


</script>
<template>
  <div class="f-container">
    <h2>Text Input</h2>
    <input v-model="text" />
    <p>{{ text }}</p>
  </div>

  <div class="f-container">
    <h2>Checkbox</h2>
    <input type="checkbox" id="myCheckbox" v-model="checked" />
    <label for="myCheckbox"> Checked: {{ checked }}</label>
  </div>

  <div class="f-container">
    <h2>Multi Checkbox</h2>
    <template v-for="name in names" :key="name">
      <p>
        <input type="checkbox" :id="name" :value="name" v-model="checkedNames" />
        <label :for="name" style="margin-left: 8px;">{{ name }}</label>
      </p>
    </template>
    <p v-if="checkedNames?.length > 0">
      {{ checkedNames }}
    </p>
  </div>

  <div class="f-container">
    <h2>Radio <span v-if="picked"> 🤩{{ picked }}</span></h2>
    <template v-for="name in names" :key="name">
      <p>
        <input type="radio" :id="`rd${name}`" :value="name" v-model="picked" />
        <label :for="`rd${name}`" style="margin-left: 8px;">{{ name }}</label>
      </p>
    </template>
  </div>
</template>
<style>
.f-container {
  border: 2px solid lightgreen;
  border-radius: 8px;
  padding: 8px 12px;
  margin: 12px 0px;
}
</style>
