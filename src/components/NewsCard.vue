<template>
   <div class="news__card">
       <!-- Компонент в блоке NEWS. Принимает обьект. В обьекте изображение, текст и ссылка -->
        <figure>
            <img class="news__card_img" :data-src="objNews.img" alt="">
            <figcaption class="news__card_figcapture">{{objNews.figcaption}}</figcaption>
        </figure>
        <h3 class="news__card_h">
            {{objNews.h}}
        </h3>
        <p class="news__card_p">
           {{objNews.p}}
        </p>
        <a class="news__card_a" href="#">Детальніше</a>
    </div>
</template>

<script>
export default {
    props:['objNews'],
}
</script>

<style lang="less">
 @import './src/assets/less/smart-grid.less';
@import './src/assets/less/mixins.less';
    .news__card{
    .col();
    .size(4);
    &_img{
        margin-bottom: 33px;
    }
    &_figcapture{
        font-size: 14px;
        line-height: 21px;
        color: #D08C00;
        margin-bottom: 35px;
    }
    &_h{
        font-size: 38px;
        font-weight: bold;
        line-height: 40px;
        color: #421100;
        margin-bottom: 43px;
    }
    &_p{
        font-size: 18px;
        line-height: 19.2px;
        color: #1D252D;
        margin-bottom: 70px;
    }
    &_a{
        font-size: 20px;
        font-weight:bold;
        line-height: 27px;
        color: #D08C00;
    }
    }
</style>