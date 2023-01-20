<template>

    <div class="photos_line_comp" v-if="photos.length > 0">
        <!-- <div class="photos_line">
              </div> -->
        <div class="photos_container">
            <div v-for="photo in photos"  v-bind:key="photo.id" class="photo_wrapper">
                <img v-bind:src="photo.thumbnailUrl"/>
            </div>
        </div>
    </div>

</template>

<script>
    export default {
        props: ['photos']
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

</style>