```vue
    <script setup lang="ts">
    import { ref } from 'vue'
    
    const firstName = ref('Dorothy')
    const lastName = ref('Vaughan')
  
    const fullName = computed(() => 
        `${firstName.value} ${lastName.value}`)
    </script>
```

```ts
export const useFullName = () => {
    const fName = ref('Dorothy')
    const lName = ref('Vaughan')
    const fullName = computed(() => `${fName.value} ${lName.value}`)
    return {fName, lName, fullName}
    }
```
```vue
    <script setup lang="ts">
    import { useFullName } from 'name'
    
    const {fName, lName, fullName} = useFullName();
    </script>
```

```ts
export const useNameStore = defineStore('name', () => {
    const fName = ref('Eduardo')
    const lName = ref('Morales')
    const fullName = computed(() => `${fName.value} ${lName.value}`)
    return { fName, lName, fullName }
})
```

```vue
    <script setup lang="ts">
    import { useNameStore } from 'stores/name'
    
    const {fName, lName, fullName} = useNameStore()
    </script>
```