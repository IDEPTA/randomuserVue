<template>
    <div class="UserList">
        <UserCard v-for="user in userList" :userItem="user"/>
        <p class="msg" v-if="userList.length == 0&&!loading">Список пока пуст</p>
        <Loader v-if="loading"/>
    </div>
</template>

<script>
import Loader from './Loader.vue'
import UserCard from './UserCard.vue';
export default {
    props:{
        userList:Object,
        loading:Boolean,
    },
    components:{
        UserCard, Loader
    },
    data() {

    }
}
</script>

<style scoped>
.UserList{
    width: 600px;
    height: 600px;
    overflow-y: auto;
    position: relative;
    background-color: teal;
    border-top-left-radius: 5px;
}
.msg{
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
    position: absolute;
    top: 40%;
    color: white;
    left: 37%;
}
@media (max-width: 800px){
    .UserList{
        width: 100%;
    }
    .msg{
        
        left: 30%;
    }
}
</style>
