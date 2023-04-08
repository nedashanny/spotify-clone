<script>
import HomeItem from '../components/HomeItem.vue';
export default{
  components:{
    HomeItem,
  }
}
</script>

<template>
  
    <p class="text-white text-capitalize fs-4 ms-1 mt-4-5-rem">Podcasts to make you smarter</p>
    <div class="d-flex ms-2 w-100 overflow-x-scroll">
      <HomeItem :imgUrl="'https://picsum.photos/200 '" :title="'item1'" :subTitle="'subtitle1'"/>
      <HomeItem :imgUrl="'https://picsum.photos/200 '" :title="'item1'" :subTitle="'subtitle1'"/>
      <HomeItem :imgUrl="'https://picsum.photos/200 '" :title="'item1'" :subTitle="'subtitle1'"/>
      <HomeItem :imgUrl="'https://picsum.photos/200 '" :title="'item1'" :subTitle="'subtitle1'"/>
      <HomeItem :imgUrl="'https://picsum.photos/200 '" :title="'item1'" :subTitle="'subtitle1'"/>
    </div>

    <p class="text-white text-capitalize fs-4 ms-1 mt-2">Recommended radio</p>
    <div class="d-flex ms-2 overflow-x-scroll">
      <HomeItem :imgUrl="'https://picsum.photos/200 '" :title="'item1'" :subTitle="'subtitle1'"/>
      <HomeItem :imgUrl="'https://picsum.photos/200 '" :title="'item1'" :subTitle="'subtitle1'"/>
      <HomeItem :imgUrl="'https://picsum.photos/200 '" :title="'item1'" :subTitle="'subtitle1'"/>
      <HomeItem :imgUrl="'https://picsum.photos/200 '" :title="'item1'" :subTitle="'subtitle1'"/>
      <HomeItem :imgUrl="'https://picsum.photos/200 '" :title="'item1'" :subTitle="'subtitle1'"/>
    </div>

    <p class="text-white text-capitalize fs-4 ms-1 mt-2">Recommended songs</p>
    <div class="d-flex ms-2 overflow-x-scroll" style="margin-bottom: 5rem;">
      <HomeItem :imgUrl="'https://picsum.photos/200 '" :title="'item1'" :subTitle="'subtitle1'"/>
      <HomeItem :imgUrl="'https://picsum.photos/200 '" :title="'item1'" :subTitle="'subtitle1'"/>
      <HomeItem :imgUrl="'https://picsum.photos/200 '" :title="'item1'" :subTitle="'subtitle1'"/>
      <HomeItem :imgUrl="'https://picsum.photos/200 '" :title="'item1'" :subTitle="'subtitle1'"/>
      <HomeItem :imgUrl="'https://picsum.photos/200 '" :title="'item1'" :subTitle="'subtitle1'"/>
    </div>
</template>
<style scoped>
  .overflow-x-scroll::-webkit-scrollbar{
    display: none;
  }
</style>