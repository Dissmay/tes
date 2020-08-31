<template>
<!-- Компонент презентации. принимает пропс с обьектом, в котором есть изображение(бэграунд) 
    а так же принимает еще один компонент текста, в компонент передается обьект
 -->
  <div class="presentation d-f pos-r">
        <img :data-src="dataPresent.image" style="width:100%; height:100%;" class="pos-a" alt="presentation image">
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
        height: 822px;
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
    }
</style>