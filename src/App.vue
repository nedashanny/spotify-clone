<script>
import { RouterLink, RouterView } from 'vue-router';
import SvgIcon from '@jamescoyle/vue-icon';
import MenuItem from './components/MenuItem.vue';
// icons
import { mdiChevronRight } from '@mdi/js';
import { mdiChevronLeft } from '@mdi/js';
import { mdiChevronDown } from '@mdi/js';
import { mdiChevronUp } from '@mdi/js';
import { mdiSpotify } from '@mdi/js';
import { mdiHomeOutline } from '@mdi/js';
import { mdiMagnify } from '@mdi/js';
import { mdiBookshelf } from '@mdi/js';
import { mdiPlus } from '@mdi/js';
import { mdiHeartOutline } from '@mdi/js';
import { mdiHeart } from '@mdi/js';
import { mdiSkipNext } from '@mdi/js';
import { mdiSkipPrevious } from '@mdi/js';
import { mdiPlayCircle } from '@mdi/js';
import { mdiVolumeHigh } from '@mdi/js';
export default {
  data(){
    return{
      iconPathes:{
        mdiVolumeHigh:mdiVolumeHigh,
        mdiPlayCircle:mdiPlayCircle,
        mdiSkipPrevious:mdiSkipPrevious,
        mdiSkipNext:mdiSkipNext,
        mdiChevronRight:mdiChevronRight,
        mdiChevronLeft:mdiChevronLeft,
        mdiChevronDown:mdiChevronDown,
        mdiChevronUp:mdiChevronUp,
        mdiSpotify:mdiSpotify,
        mdiHomeOutline:mdiHomeOutline,
        mdiMagnify:mdiMagnify,
        mdiBookshelf:mdiBookshelf,
        mdiPlus:mdiPlus,
        mdiHeartOutline:mdiHeartOutline,
        mdiHeart:mdiHeart

      },
      mdiChevronDownVisible:false,
      mdiChevronUpVisible:true,
      
      menuItemMatchUrl:false,
      menuItems:[
        {
          iconPath:mdiHomeOutline,
          iconText:'Home',
          isActive:localStorage.getItem('spotify-clone-current-page')==='/',
          url:'/'
        },
        {
          iconPath:mdiMagnify,
          iconText:'search',
          isActive:localStorage.getItem('spotify-clone-current-page')==='/search',
          url:'/search'
        },
        {
          iconPath:mdiBookshelf,
          iconText:'library',
          isActive:localStorage.getItem('spotify-clone-current-page')==='/library',
          url:'/library'
        }
      ]

    }
  },
  methods:{
    toggleMenuVisibility(){
      this.mdiChevronDownVisible=!this.mdiChevronDownVisible
      this.mdiChevronUpVisible=!this.mdiChevronUpVisible
    },
    isMenuItemMatchUrl(iconText){
      if(iconText==this.$route.name){
        this.menuItemMatchUrl=true
      }
    },
    menuItemisActive(url){
      this.menuItems.forEach(item => {
        if(url!=item.url){
          item.isActive=false
        }else{
          item.isActive=true
        }
        localStorage.setItem('spotify-clone-current-page',url)
      });
    }
  },
  mounted(){
    this.$router.push('/')
    this.menuItemisActive('/');
  },
  components: {
    SvgIcon,RouterLink,RouterView,MenuItem
  },
}
</script>

<template>
  
  
  <div class="profile width-15rem position-fixed end-0 d-flex justify-content-between align-items-center z-2" style="background-color: rgb(65, 65, 65);">
      <div class="d-flex">
        <svg-icon type="mdi" :path="iconPathes.mdiChevronLeft" :size="30" class="bg-dark p-1 rounded-circle ms-4" color="#fff"></svg-icon>
        <svg-icon type="mdi" :path="iconPathes.mdiChevronRight" :size="30" class="bg-dark p-1 rounded-circle ms-3" color="#fff"></svg-icon>
      </div>
      <!-- drop down -->
      <div>
        <li class="dropdown d-flex align-items-center">
          <button @click="toggleMenuVisibility()" class="d-flex align-items-center rounded-pill me-1 btn btn-dark" data-bs-toggle="dropdown">
            <img src="https://picsum.photos/200" class="rounded-circle" alt="">
            <p class="text-white ms-1 mt-3 fs-6">Konjed khatoon</p>
            <svg-icon type="mdi" :path="iconPathes.mdiChevronDown" :size="25" class="rounded-circle ms-1 mt-1" :class="{'d-none':mdiChevronDownVisible,'d-block':mdiChevronUpVisible}" color="#fff"></svg-icon>
            <svg-icon type="mdi" :path="iconPathes.mdiChevronUp" :size="25" class="rounded-circle ms-1 mt-1" :class="{'d-none':mdiChevronUpVisible,'d-block':mdiChevronDownVisible}" color="#fff"></svg-icon>
          </button>
          <ul class="dropdown-menu dropdown-menu-dark">
            <li><a class="dropdown-item" href="#">Profile</a></li>
            <li><a class="dropdown-item" href="#">Logout</a></li>
          </ul>
        </li>
      </div>
  </div>
  <!-- SIDE MENU -->
  <div class="side-menu bg-dark position-fixed p-3">
    <RouterLink to="/" class="text-decoration-none">
      <div class="d-flex align-items-center">
        <svg-icon type="mdi" :path="iconPathes.mdiSpotify" :size="50" class="rounded-circle ms-1 mt-1" color="#fff"></svg-icon>
        <p class="fs-2 mt-3 ms-2 text-white d-sm-block d-none">Spotify</p>
      </div>
    </RouterLink>

    <!-- menu items -->

    <div v-for="(item,index) in menuItems" :key="index" @click="menuItemisActive(item.url)" >
      <RouterLink :to="item.url" class="text-decoration-none">
        <MenuItem :iconText="item.iconText" :isActive="item.isActive">
          <svg-icon type="mdi" :path="item.iconPath" :size="25" class="ms-1" color="#fff"></svg-icon>
        </MenuItem>
      </RouterLink>
    </div>
    

    <p class="text-capitalize text-white mt-4 ms-1">playlists</p>

    <RouterLink to="/library" class="text-decoration-none">
      <MenuItem :iconText="'Create Playlist'">
        <div class="d-flex justify-content-center align-items-center menu-item-square menu-item-gray ms-1"> 
          <svg-icon type="mdi" :path="iconPathes.mdiPlus" :size="25" class="p-1" color="#000"></svg-icon>
        </div>
      </MenuItem>
    </RouterLink>

    <RouterLink to="/library" class="text-decoration-none">
      <MenuItem :iconText="'Liked Songs'">
        <div class="d-flex justify-content-center align-items-center menu-item-square menu-item-gradient ms-1"> 
          <svg-icon type="mdi" :path="iconPathes.mdiHeart" :size="25" class="p-1" color="#fff"></svg-icon>
        </div>
      </MenuItem>
    </RouterLink>

    <div class="border-top border-light w-100 my-4"></div>

    <div>
      <p class="text-capitalize text-white fs-6 fw-lighter text-secondary">playlists</p>   
      <p class="text-capitalize text-white fs-6 fw-lighter text-secondary">playlists</p>
      <p class="text-capitalize text-white fs-6 fw-lighter text-secondary">playlists</p>
    </div>
    
  </div>
  <div class="position-fixed end-0 top-0 width-15rem h-100 overflow-auto z-1 dark-gradient">
    <RouterView class="berder-0 p-1 mb-5"  style="width: 100% !important; height: 100%; !important" />
  </div>

  <!-- player -->

  <div class="position-fixed bottom-0 end-0 w-100 m-0 row align-items-center bg-black player" style="height: 4.5rem; z-index: 50;">
      <div class="col-8 col-md-3">
      <div class="d-flex justify-content-start align-items-center">
        <img src="https://picsum.photos/200" alt="" style="width: 3rem; height: 3rem;">
        <div class="ms-1">
          <p class="text-white text-capitalize fw-bolder fs-6 m-0">if i get high</p>
          <p class="text-capitalize text-secondary-emphasis fs-6 m-0">if i get high</p>
        </div>
        <svg-icon type="mdi" :path="iconPathes.mdiHeart" :size="20" class="p-1 m-2" color="#50C878"></svg-icon>
      </div>
    </div>

    <div class="col-6 d-md-block d-none">
      <div class="d-flex flex-column justify-content-center align-items-center p-0">
        <div class="mt-2">
          <svg-icon type="mdi" :path="iconPathes.mdiSkipPrevious" :size="25" class="me-4" color="#fff"></svg-icon>
          <svg-icon type="mdi" :path="iconPathes.mdiPlayCircle" :size="30" class="" color="#fff"></svg-icon>
          <svg-icon type="mdi" :path="iconPathes.mdiSkipNext" :size="25" class="ms-4" color="#fff"></svg-icon>
        </div>
        <div class="d-flex align-items-center">
          <p class="text-white fs-6 m-1">0:00</p>
          <div class="progress bg-secondary player-progress" role="progressbar" aria-label="Example 1px high" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100">
            <div class="progress-bar bg-light" style="width: 50%"></div>
          </div>
          <p class="text-white fs-6 m-1">4:05</p>
        </div>
      </div>
    </div>

    <div class="col-3 d-md-block d-none">
      <div class="d-flex justify-content-end align-items-center">
        <svg-icon type="mdi" :path="iconPathes.mdiVolumeHigh" :size="32" class="p-1 m-2" color="#fff"></svg-icon>
        <div class="progress bg-secondary" role="progressbar" aria-label="Example 1px high" aria-valuenow="25" aria-valuemin="0" aria-valuemax="100" style="height: 1px; width: 5rem;">
          <div class="progress-bar bg-light" style="width: 25%"></div>
        </div>
      </div>
    </div>
    </div>
</template>