<script>

</script>

<template>

    <div class="parent">
        <div class="block">
            <div>
                <div class="sub_block_tab_left round_tab">
                    Каталог
                </div>
                <div class="sub_block_tab_right round_tab">
                    <div class="favorites_icon"></div>
                    <div class="right_tab_name">Избранное</div>
                </div>
            </div>
            <div class="sub_block_content">
                <div class="user_line_comp">
                    <div class="user_line">
                        <div class="user_row_icon row_icon expand_icon"></div>
                        <div class="user_name"> user name </div>
                    </div>
                </div>
                <div class="user_line_comp">
                    <div class="user_line">
                        <div class="user_row_icon row_icon collaps_icon"></div>
                        <div class="user_name"> user name </div>
                    </div>
                    <div class="album_line_comp">
                        <div class="album_line">
                            <div class="album_row_icon row_icon expand_icon"></div>
                            <div class="user_name"> album name </div>
                        </div>
                    </div>
                    <div class="album_line_comp">
                        <div class="album_line">
                            <div class="album_row_icon row_icon collaps_icon"></div>
                            <div class="user_name"> album name </div>
                        </div>
                        <div class="photos_line_comp">
                            <!-- <div class="photos_line">
              </div> -->

                            <div class="photos_container">
                                <div class="photo_wrapper">
                                    <img src="https://via.placeholder.com/150/a91759" />
                                </div>
                                <div class="photo_wrapper">
                                    <img src="https://via.placeholder.com/150/a91759" />
                                </div>
                                <div class="photo_wrapper">
                                    <img src="https://via.placeholder.com/150/a91759" />
                                </div>
                                <div class="photo_wrapper">
                                    <img src="https://via.placeholder.com/150/a91759" />
                                </div>
                                <div class="photo_wrapper">
                                    <img src="https://via.placeholder.com/150/a91759" />
                                </div>
                                <div class="photo_wrapper">
                                    <img src="https://via.placeholder.com/150/a91759" />
                                </div>
                                <div class="photo_wrapper">
                                    <img src="https://via.placeholder.com/150/a91759" />
                                </div>
                                <div class="photo_wrapper">
                                    <img src="https://via.placeholder.com/150/a91759" />
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
                <div class="user_line_comp">
                    <div class="user_line">
                        <div class="user_row_icon row_icon expand_icon"></div>
                        <div class="user_name"> user name </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<style>
.parent {
    width: 100%;
    height: 100%;
    position: absolute;
    top: 0;
    left: 0;
    overflow: auto;
    background-color: rgb(196, 242, 252);
}

/* .block {
    width: 600px;
    height: 400px;
    position: absolute;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    margin: auto;
    border: 1px solid #aaa;
} */

.sub_block_tab_left {
    float: left;
    background-color: brown;
}

.sub_block_tab_right {
    /* left: 150px; */
    float: right;
    background-color: blue;
}

.round_tab {
    width: 50%;
    height: 30px;
    border-top-left-radius: 7px;
    border-top-right-radius: 7px;
    font-family: serif;
}

.sub_block_content {
    width: 100%;
    /* height: 370px; */
    background-color: chartreuse;
    float: inline-end;
    clear: both;
}

.favorites_icon {
    margin-top: 2px;
    /* padding-top: 5px; */
    /* width: 20px; */

    width: 25px;
    height: 25px;

    display: inline-block;


    background: url("../assets/favorites.ico") no-repeat left center;
    background-size: 20px;
    vertical-align: bottom;
}

.right_tab_name {
    display: inline-block;
    /* float: left; */
}

.user_row_icon {
    margin-left: 40px;
}

.album_row_icon {
    margin-left: 80px;
}

.row_icon {
    /* margin-top: 5px; */
    /* padding-top: 5px; */
    width: 30px;
    height: 30px;

    background-size: 30px;
    /* display:inline-block;
  vertical-align:bottom; */
    margin-top: 5px;
    float: left;
}

.expand_icon {
    background: url(../assets/add.ico) no-repeat left center;
}

.collaps_icon {
    background: url(../assets/collaps.ico) no-repeat left center;
}


.user_line {
    /* float: left; */
    height: 40px;
    background-color: blueviolet;
    border: 1px solid #aaa;
}

.album_line {
    /* float: left; */
    height: 40px;
    background-color: blueviolet;
    border: 1px solid #aaa;
}

.photos_line {
    /* float: left; */
    height: 40px;
    background-color: blueviolet;
    border: 1px solid #aaa;
}

/* .photos_container {
    background-color: coral;
    border: 1px solid #aaa;
    margin-left: 160px;
    padding-top: 20px;
    padding-left: -40px;
    display: inline-block;
} */

.photo_wrapper {
    height: 100px;
    width: 100px;
    margin-top: 20px;
    margin-left: 15px;
    margin-right: 15px;
    float: left;
}

.photo_wrapper img {
    object-fit: cover;
    width: 100%;
    height: 100%;
    border-radius: 3px;
}

.user_name {
    margin-left: 20px;
    margin-top: 8px;
    float: left;
}

.dot {
    height: 25px;
    width: 25px;
    background-color: #bbb;
    border-radius: 50%;
    margin-left: 30px;
    margin-top: 7px;
    /* display: inline-block; */
}

.user_line_comp {
    display: block;
}
</style>