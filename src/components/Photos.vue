<template>

    <div class="photos_line_comp" v-if="photos.length > 0">
        <!-- <div class="photos_line">
              </div> -->
        <div class="photos_container">
            <div v-for="photo in photos"  v-bind:key="photo.id" class="photo_line">
                <div class="photo_favotive_wrapper">
                    <img src="../assets/photo_not_favorite.ico" />
                </div>
                <div class="photo_wrapper">
                    <img v-bind:src="photo.thumbnailUrl" />
                </div>
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