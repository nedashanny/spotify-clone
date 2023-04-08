<script>
import CategorySelect from '../components/CategorySelect.vue';

export default{
  components:{
    CategorySelect
  }
}
</script>
<template>
    <p class="text-white text-capitalize fs-4 ms-1 mt-4-5-rem">Podcasts to make you smarter</p>
    <div class="d-flex flex-wrap ms-2" style="margin-bottom: 5rem;">
        <CategorySelect :categoty="'cat 1'"/>
        <CategorySelect :categoty="'cat 2'"/>
        <CategorySelect :categoty="'cat 3'"/>
        <CategorySelect :categoty="'cat 4'"/>
        <CategorySelect :categoty="'cat 5'"/>
    </div>
</template>