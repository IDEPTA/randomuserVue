<template>
  <div class='MainContainer'>
    <h2>Список пользователей</h2>
    <UserList :userList="usersList" :loading="loading" />
    <button @click="sendUsers" type="button">Тык</button>
  </div>
</template>

<script>
import UserList from './components/UserList.vue'
export default {
  components: {
    UserList
  },
  data() {
    return {
      usersList: [],
      loading:false,
    }
  },
  methods: {
    async sendUsers() {
      this.loading = true
      this.usersList = []
      let users = await (await fetch("https://randomuser.me/api/?results=10")).json()
      await users.results.forEach(element => {
        this.usersList.push(element)
      });
      this.loading = false
    }
  }
}
</script>

<style>
.MainContainer {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
}

.MainContainer button {
  padding: 10px 0px;
  width: 600px;
  background-color: teal;
  border: none;
  color: white;
  font-size: 20px;
  border-radius: 0px 0px 5px 5px;
  cursor: pointer;
  transition: 0.5s;
}
.MainContainer h2{
  color: white;
  font-family:Verdana, Geneva, Tahoma, sans-serif;
}
@media (max-width: 800px){
    .MainContainer button{
        width: 100%;
    }
}
</style>
