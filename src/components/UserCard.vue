<template>
    <div class="userCard">
        <img :src=userItem.picture.large alt="image">
        <div class="userCardInfo">
            <p>
                {{ userItem.name.title }} {{ userItem.name.first }} {{ userItem.name.last }}
            </p>
            <p>Пол: {{ userItem.gender }}</p>
            <p>Локация: {{ userItem.location.city }} {{ userItem.location.state }} {{ userItem.location.country }}</p>
            <p  class="email">Почта: {{ userItem.email }}</p>
            <p>Телефон: {{ userItem.phone }}</p>
        </div>


    </div>
</template>
<script>
export default {
    props: {
        userItem: Object,
    },
    data() {
        return {

        }
    }
}
</script>
<style>
.userCard {
    display: flex;
    margin: 10px;
    background-color: rgb(219, 219, 219);
    border-radius: 5px;
}
img{
    width: 30%;
    border-top-left-radius: 5px;
    border-bottom-left-radius: 5px;
}
.userCardInfo{
    margin-left: 10px;
    font-family:Verdana, Geneva, Tahoma, sans-serif;
}
@media (max-width: 800px){
    img{
        width: auto;
    }
    .userCardInfo{
        font-size: 14px;
    }
    .email{
        display: none;
    }
}
</style>