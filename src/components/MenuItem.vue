<script>
    export default{
        props:{
            iconText:String,
            isActive:Boolean
        },
    }
</script>
<template>
    <div class="d-flex justify-content-center justify-content-sm-start align-items-center m-0 menu-item" :class="{'bg-black':isActive}" >
        <div class="p-2">
            <slot></slot>
        </div>
        <p class="fs-6 mt-3 ms-2 text-white d-sm-block d-none">{{ iconText }}</p>
    </div>
</template>