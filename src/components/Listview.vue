<template>
  <div class="container" v-if="users.length">
    <h1>Connected Members</h1>
    <table>
      <tr>
        <th>Id</th>
        <th>Name</th>
        <th>Email</th>
        <th>Gender</th>
        <th>Status</th>
      </tr>
      <tr class="user-table" v-for="user in users" :key="user.id">
        <td>{{ user.id }}</td>
        <td>{{ user.name }}</td>
        <td>{{ user.email }}</td>
        <td>{{ user.gender }}</td>
        <td :class="{ active: user.status === 'active' }">{{ user.status }}</td>
      </tr>
    </table>
  </div>
  <div v-else>Loading...</div>
</template>

<script>
import {onMounted, ref} from 'vue'
export default {
setup(){
    let users = ref([])
    const uri = 'https://gorest.co.in/public/v1/users'
    const token = '?access-token=d7c01847de4c083cb154e9a533294301e9f05f93dbae7d589e42ece63226c0a3'


    onMounted(async () => {
    try {
    const url = uri + token
    const res = await fetch(url)
    const data = await res.json()
    users.value = data.data
    } catch (error) {
      console.log(error)
    }
  })
  return {users}
}
}
</script>

<style>
</style>