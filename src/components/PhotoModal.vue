<template>
    <div id="photo_modal_wrapper">
        <div class="close_modal" @click="$emit('close_modal')"></div>
        <div class="photo_modal_image">
            <img v-bind:src="modalPhotoUrl"/>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['modalPhotoUrl']
    }
</script>
