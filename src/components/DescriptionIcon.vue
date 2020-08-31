<template>
<!-- Компонент описывающий приемущества
    в компоненте 1 изображение, и две подписи
 -->
    <div class="descriptionIcon">
        <img class="descriptionIcon__img" src="" :data-src="dataIcon.icon" alt="">
        <p class="descriptionIcon__top">
            {{dataIcon.textTop}}
        </p>
        <p class="descriptionIcon__bottom">
            {{dataIcon.textBottom}}
        </p>
    </div>
</template>

<script>
export default {
    props:['dataIcon']

}
</script>

<style lang="less">

   .descriptionIcon{
       text-align: center;
       margin-top: -40px;
       &__img{
           margin-bottom: 25px;
       }
       &__top{
           font-size: 30px;
           color: #421100;
           font-weight: bold;
            text-align: center;
       }
       &__bottom{
           font-size: 16px;
           color: #D08C00;
            text-align: center;
       }
   }
</style>