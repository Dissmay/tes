<template>
<!-- Компонент принимает класс позиции текста, принимает обьект стия, текст, линк -->
   <div :class="text.positionText ? 'd-f textComponent' + ' ' + text.positionText : 'd-f textComponent' " 
        v-bind:style="text.styleObject"
        >
        <h2 :style="{marginBottom : text.styleObject.marginBottom}">
            {{text.headingText}}
        </h2>
        <p v-for="(p, i) in text.text" :key="i">
            {{p}}
        </p>
  
        <a class="textComponent__link" href="/" v-bind:style="{color: text.styleObject.color}">{{text.link}}
            <i class="fa fa-long-arrow-right" aria-hidden="true"></i>
        </a>
    </div>
</template>

<script>
export default {
    props:['text']
}
</script>

<style lang="less" scoped>
  @import './src/assets/less/smart-grid.less';
  @import './src/assets/less/mixins.less';
    .textComponent{
        flex-direction: column;
        justify-content: center;
        z-index: 10;
        word-wrap: break-word;
        h2{
            font-size: 48px;
            margin-bottom: 95px;
            font-family: 'Gilroy-Bold';
            line-height: 50px;
        }
        p{
            margin-bottom: 62px;
        }
        a{
            color: #ffffff;
            position: relative;
            .fa{
               position: absolute;
               top: 5px;
               left: 95px;
            }           
        }
        &.right{
            .shift-left(4.5);
        }
        &.left{
            .shift-left(2);
        }
    }
</style>