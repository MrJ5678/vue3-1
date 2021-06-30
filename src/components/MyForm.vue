<!--
 * @Author: hhhhhq
 * @Date: 2021-06-30 11:24:20
 * @LastEditors: hhhhhq
 * @LastEditTime: 2021-06-30 16:11:55
 * @Description: file content
-->
<template>
  <div>
    <!-- <p>{{ name }}</p> -->
    <input ref="el" type="text" placeholder="Name" v-model="name" />
    <div>
      <button @click="submitForm" :disabled="name.length === 0">Submit</button>
    </div>
  </div>
</template>

<script>
import { ref, onMounted } from "vue"
export default {
  setup() {
    const name = ref("")
    const el = ref()

    onMounted(() => {
      el.value.focus()
    })

    const submitForm = () => {
      console.log(`Form submitted! Name = ${name.value}`)
    }

    return {
      el,
      name,
      submitForm,
    }
  },
}
</script>

<style scoped>
input[type="text"] {
  padding: 5px;
}

button {
  margin-top: 20px;
}
</style>
