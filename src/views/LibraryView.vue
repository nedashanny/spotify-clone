<script>
import SvgIcon from '@jamescoyle/vue-icon';
import SongRow from '../components/SongRow.vue'
// icons
import { mdiPlayCircle } from '@mdi/js';
import { mdiPauseCircle } from '@mdi/js';
import { mdiHeart } from '@mdi/js';
import { mdiDotsHorizontal } from '@mdi/js';
import { mdiClockOutline } from '@mdi/js';
export default{
    data(){
    return{
      iconPathes:{
        mdiPlayCircle:mdiPlayCircle,
        mdiPauseCircle:mdiPauseCircle,
        mdiHeart:mdiHeart,
        mdiDotsHorizontal:mdiDotsHorizontal,
        mdiClockOutline:mdiClockOutline,
      },
    }
  },
  components:{
    SvgIcon,SongRow
  }
}
</script>
<template>
    <p class="text-white text-capitalize fw-bolder fs-4 ms-3 mt-4-5-rem">crown of thorns</p>
    <div class="p-3" style="margin-bottom: 5rem;">
        <!-- card -->
        <div class="card library-card mb-3 berder-0">
            <div class="row justify-content-center g-0">
                <div class="col-sm-4">
                    <img src="https://picsum.photos/200" class="img-fluid" alt="...">
                </div>
                <div class="col-sm-8">
                    <div class="card-body text-white">
                        <h5 class="card-title text-capitalize">crown of thorns</h5>
                        <div class="d-flex">
                            <p class="card-text ms-1"><small class="text-white-50">Album</small></p>
                            <div class="ms-2" style="border-radius: 100%; width: 4px; height: 4px; background-color: #adb5bd; margin-top: 0.75rem;"></div>
                            <p class="card-text ms-2"><small class="text-white-50">2020</small></p>
                            <div class="ms-2" style="border-radius: 100%; width: 4px; height: 4px; background-color: #adb5bd; margin-top: 0.75rem;"></div>
                            <p class="card-text ms-2"><small class="text-white-50">11 songs</small></p>
                        </div>
                        <div class="d-flex justify-content-center justify-content-sm-start align-items-center">
                        <div class="m-sm-1">
                            <svg-icon v-if="true" type="mdi" :path="iconPathes.mdiPlayCircle" :size="30" color="#fff"></svg-icon>
                            <svg-icon v-else type="mdi" :path="iconPathes.mdiPauseCircle" :size="30" color="#fff"></svg-icon>
                        </div>
                        <svg-icon class="m-1" type="mdi" :path="iconPathes.mdiHeart" :size="23" color="#50C878"></svg-icon>
                        <svg-icon class="m-1" type="mdi" :path="iconPathes.mdiDotsHorizontal" :size="23" color="#fff"></svg-icon>
                    </div>
                    </div>
                </div>
            </div>
        </div>
        <!-- songs -->
        <div class="mt-4">
            <div style="height: 2rem" class="d-flex justify-content-between mt-1 align-items-center w-100 border border-start-0 border-end-0 border-top-0 border-dark-subtle">
                <div class="d-flex">
                    <p class="text-secondary-emphasis ms-2">#</p>
                    <p class="text-secondary-emphasis ms-2">item</p>
                </div>
                <svg-icon class="m-1" type="mdi" :path="iconPathes.mdiClockOutline" :size="15" color="#adb5bd"></svg-icon>
            </div>
            <div class="mt-2">
                <SongRow :index="1" :artist="'Efisio Cross'" :name="'I will never abandin you'"/>
                <SongRow :index="2" :artist="'Efisio Cross'" :name="'if you belive'"/>
                <SongRow :index="3" :artist="'Efisio Cross'" :name="'if you fall i will carry you'"/>
                <SongRow :index="4" :artist="'Efisio Cross'" :name="'as long as god loves us'"/>
                <SongRow :index="5" :artist="'Efisio Cross'" :name="'crown of thorns'"/>
            </div>
        </div>

    </div>
</template>