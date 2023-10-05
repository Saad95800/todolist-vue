<script setup>
import { ref } from 'vue'

defineProps({
  title: String,
})

const count = ref(0); // Variable réactive (ou un state)
const active = ref(true); 
const items = ref([{ message: 'Foo' }, { message: 'Bar' }, { message: 'toto' }]);
const item = ref({ message: 'Foo' });
const {message} = item;
const visible = ref(true);
</script>

<template>
  <h1>{{ title }}</h1>
    <ul>
      <li v-for="item in items">
        {{ item.message }}
      </li>      
    </ul>

{{ message }}
  <div class="card">
    <button v-if="visible" v-show="true" v-once type="button" @click="count++">count is {{ count }}</button>
    <p>{{ count }}</p>
  </div>
</template>