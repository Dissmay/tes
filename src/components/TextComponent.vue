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
        .media(1250px,{
            width: 100% !important;
            z-index:2;
        });
        .media(450px,{
            max-width: 90%;
            padding-right: 30px;
        });
        h2{
            font-size: 48px;
            margin-bottom: 95px;
            font-family: 'Gilroy-Bold';
            line-height: 50px;
            .media(1250px,{
                margin-bottom: 20px;
                font-size: 40px;
                z-index:2;
            });
        }
        p{
            margin-bottom: 62px;
            font-size: 18px;
            font-family: 'Girloy';
            .media(1250px,{
                margin-bottom: 20px;
                z-index:2;
            });
        }
        a{
            color: #ffffff;
            position: relative;
            font-family: 'Girloy-Bold';
            .media(1250px,{
                z-index:2;
            });
            .fa{
               position: absolute;
               top: 5px;
               left: 95px;
            }           
        }
        &.right{
            .shift-left(4.5);
            .media(1250px,{
                .shift-left(0);
            });
        }
        &.left{
            .shift-left(2);
            .media(1250px,{
                .shift-left(0);
            });
        }
    }
</style>