<template>

    <div class="photos_line_comp" v-if="photos.length > 0">
        <!-- <div class="photos_line">
              </div> -->
        <div class="photos_container">
            <Photo v-for="photo in photos"  v-bind:key="photo.id" v-bind:photo="photo"/>
        </div>
    </div>

</template>

<script>

    import Photo from './Photo.vue'

    export default {
        props: ['photos'],
        components: {Photo}
    }

</script>

   

<style>

.photos_container {
    background-color: coral;
    border: 1px solid #aaa;
    margin-left: 160px;
    padding-left: -40px;
    padding-bottom: 10px;
    /* display: inline-block; */
    float: left;
}


.photo_line {
    float: left;    
}

.photo_favotive_wrapper {
    /* display: inline-block; */
    float: left;
    height: 25px;
    width: 25px;
    position: absolute;
    margin-left: 86px;
    margin-top: 23px;
}

.photo_favotive_wrapper img {
    object-fit: cover;
    width: 100%;
    height: 100%;
}

</style>