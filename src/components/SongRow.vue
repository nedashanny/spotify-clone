<script>
import SvgIcon from '@jamescoyle/vue-icon';
import { mdiPlay } from '@mdi/js';
import { mdiHeart } from '@mdi/js';
export default{
    props:{
        index:Number,
        artist:String,
        name:String,
    },
    data(){
        return{
            mouseOver:null,
            iconPathes:{
                mdiPlay:mdiPlay,
                mdiHeart:mdiHeart,
            },
        }
    },
    components:{
        SvgIcon
    }
}
</script>
<template>
    <div class="w-100 m-1">
        <li class="d-flex justify-content-between align-items-center" @mouseenter="mouseOver=true" @mouseleave="mouseOver=false">
            <div class="d-flex align-items-center">
                <div> 
                    <div v-if="mouseOver" style="width: 2rem; height: 2rem;" class="d-flex justify-content-center align-items-center">
                        <svg-icon class="m-1" type="mdi" :path="iconPathes.mdiPlay" :size="30" color="#adb5bd"></svg-icon>
                    </div>
                    <div v-else style="width: 2rem; height: 2rem;" class="d-flex justify-content-center align-items-center">
                        <p class="text-white mt-3">{{ index }}</p>
                    </div>
                </div>
                <div class="ms-2">
                    <p style="margin: 0; padding: 0;" class="text-white fw-bold">{{ artist }}</p>
                    <p style="margin: 0; padding: 0;" class="text-secondary-emphasis">{{ name }}</p>
                </div>
            </div>
            <div class="d-flex">
                <div v-if="mouseOver" style="width: 2rem; height: 2rem;" class="d-flex justify-content-center align-items-center">
                    <svg-icon class="m-1" type="mdi" :path="iconPathes.mdiHeart" :size="15" color="#50C878"></svg-icon>
                </div>
                <div style="width: 2rem; height: 2rem;" class="d-flex justify-content-center align-items-center">
                    <p class="text-white mt-3"><small>4:15</small></p>
                </div>
            </div>
        </li>
    </div>
</template>

<style scoped>
 li{
    list-style-type: none;
    cursor: pointer;
    border-radius: 0.5rem;
 }
 li:hover{
    background-color: rgb(68, 68, 68);
 }
</style>