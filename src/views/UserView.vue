<!-- eslint-disable prettier/prettier -->
<script setup>

import UserSummary from "../components/UserSummary.vue";
import { ref, onMounted } from "vue"

let users = ref([])

onMounted(async () => {
  const response = await fetch("https://reqres.in/api/users")
  const data = await response.json()
  users.value = ref(data.data)
  console.log(users.values)
})

</script>

<template>
  <Suspense>
    <div>
      <h1>Users</h1>
      <div v-for="user in users.value">
        <UserSummary :user="user" />
      </div>
    </div>
  </Suspense>
</template>
