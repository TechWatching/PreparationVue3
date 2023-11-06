```vue
<script setup lan="ts">
  import {ref, reactive, computed, watch} from "vue"

  const programmingLanguage = ref("Fortran")

  const developer = reactive({firstname: "Dorothy", surname: "Vaughan"})

  const fullname = computed(() => `${developer.firstname} ${developer.surname}!`.toUpperCase())

  watch(programmingLanguage, (newLanguage, previousLanguage) => {
    console.log(`Programming languaged changed from ${previousLanguage} to ${newLanguage}`);
  });
</script>

<template>
  <h1>Hello {{ fullname }}</h1>
  <div><label>Firstname <input v-model="developer.firstname"></label></div>
  <div><label>Surname <input v-model="developer.surname"></label></div>
  <div><label>Programming Language<input v-model="programmingLanguage"></label></div>
</template>
```