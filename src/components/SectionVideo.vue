<template>
    <section class="sectionVideo">
        <div v-if="!video" class="sectionVideo__bgc" data-src="https://i.ibb.co/zxPvGnf/2.jpg">
            <div class="backgroundFilter"></div>
            <div @click="video = !video" class="sectionVideo__btnPlay"></div>
        </div>
        <div v-if="video" class="video-width">
            <div class="video-height">
                <iframe  src="https://www.youtube.com/embed/DCuIBLeY6H8?autoplay=1&origin=http" allow='autoplay' frameborder="0"  allowfullscreen></iframe>
            </div>
        </div>
    </section>
</template>

<script>
export default {
    data(){
        return{
            video:false
        }
    }
}
</script>

<style lang="less">
.backgroundFilter{
    background-color: #11171D;
    top: 0;
    left: 0;
    bottom: 0;
    right: 0;
    opacity: 0.3;
    position: absolute;
}
.sectionVideo{
    &__bgc{
        position: relative;
        background-position: center center;
        width: 100%;
        height: 838px;
        display: flex;
        background-size: cover;
        justify-content: center;
        align-items: center;
    }
    &__btnPlay{
        width: 137px;
        height: 137px;
        border-radius: 50%;
        border:1px solid white;
        position: relative;
        cursor: pointer;
        &:after{
            position: absolute;
            content:'';
            color: white;
            top: 50%;
            left: 50%;
            border: 20px solid transparent; border-left: 30px solid white;
            transform: translate(-20%, -50%);
        }
    }
}
.wideo-width{
  width: 100%;
  height: 0;
}

.video-height{
  width: 100%;
  padding-top: 50%; /* проценты от ширины video-width */
  position: relative;
}

.video-height iframe{
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
}
</style>