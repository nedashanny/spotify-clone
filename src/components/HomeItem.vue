<script>
    import { RouterLink } from 'vue-router';
    export default{
        props:{
            title:String,
            subTitle:String,
            imgUrl:String
        },
        components:{
            RouterLink
        }
    }
</script>
<template>
    <router-link class="text-decoration-none" to="library">
        <div class="card text-bg-dark berder-0 m-1 width-fit-content">
            <img :src=imgUrl class="card-img-top berder-0 p-2" alt="..." style="width: 12rem;">
            <div class="card-body">
                <h5 class="card-title">{{ title }}</h5>
                <p class="card-text">{{ subTitle }}</p>
            </div>
        </div>
    </router-link>
</template>