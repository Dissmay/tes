<template>
<!-- Компонент презентации. принимает пропс с обьектом, в котором есть изображение(бэграунд) 
    а так же принимает еще один компонент текста, в компонент передается обьект
 -->
  <div class="presentation d-f pos-r">
        <img :data-src="dataPresent.image" class="pos-a presentation__img" alt="presentation image">
        <!-- <div  class="presentation__video-width pos-a"  style="width:100%; height:100%;">
            <div class="presentation__video-height" style="width:100%; height:100%;">
                <iframe style="width:100%; height:100%;" class="videoPresent" rel="preconnect"  data-src="https://www.youtube.com/embed/DCuIBLeY6H8?autoplay=1&mute=1&showinfo=10&controls=0&origin=http" allow='autoplay' mute=1 frameborder="0"  allowfullscreen></iframe>
            </div>
        </div> -->
        <div class="presentation__filterImg" :style="{backgroundColor: dataPresent.backgroundColor }"></div>
        <TextComponent :text="dataPresent"/>
    </div>
</template>

<script>
import TextComponent from './TextComponent'
export default {
    props:['dataPresent'],
    components:{
        TextComponent
    }

}
</script>

<style lang="less">
  @import './src/assets/less/smart-grid.less';
  @import './src/assets/less/mixins.less';
    .presentation{
        width: 50%;
        padding-top: 15.188rem;
        padding-bottom: 11.3rem;
        .media(1250px,{
            width: 100%;
        });
        position: relative;
        background-size: cover;
        background-repeat: no-repeat;
        background-position: center bottom;
        &__filterImg{
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background-color: #421100;
            opacity: 0.7;
        }
        &__img{
            top: 0;
            width: 100%;
            height: 100%;
        }
    }
.presentation__video-width{
    width: 100%;
}
</style>