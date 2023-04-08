<script>
import{RouterLink}from'vue-router'
import uniqolor from 'uniqolor' 
export default{
    props:{
        categoty:String,
    },
    components:{
        RouterLink
    },
    data(){
        return{
            uniqolor:uniqolor.random().color
        }
    }
}
</script>
<template>
    <RouterLink to="library" class="text-decoration-none m-1">
        <div v-if="uniqolor" class="overflow-hidden position-relative rounded categotry" :style="`background-color:${uniqolor}`">
            <p class="text-white fw-bolder text-capitalize m-2">{{categoty}}</p>
            <img src="https://picsum.photos/200" class="position-absolute bottom-0" alt="">
        </div>
    </RouterLink>
</template>