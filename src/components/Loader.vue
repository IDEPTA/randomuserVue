<template>
    <div class="loader">
        
    </div>
</template>
<script>
export default{
    data(){

    }
}
</script>
<style>
.loader{
    width: 30px;
    height: 30px;
    border-top:4px solid rgb(39, 39, 39);
    border-left:4px solid rgb(255, 255, 255);
    border-right:4px solid rgb(255, 255, 255);
    border-bottom:4px solid rgb(255, 255, 255);
    border-radius: 100%;
    animation: load 0.5s infinite linear;
    position: absolute;
    top: 40%;
    left: 45%;
}
@keyframes load {
  100% {transform: rotate(360deg);}
}
</style>