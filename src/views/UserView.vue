<!-- eslint-disable prettier/prettier -->
<script setup>

import { ref } from "vue"

let users = ref([])

fetch("https://reqres.in/api/users")
.then( (response) => response.json() )
.then( (data) => { users.value = data.data })

</script>

<template>
  <div>
      <h1>Users</h1>
    <ul>
      <li v-for="user in users">
        {{ user.first_name }} {{ user.last_name }}
      </li>
    </ul>
  </div>
</template>