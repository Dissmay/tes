<template>
  <header class="">
    <div class="row align-items-center header">
      <!-- Логотип -->
      <a href="/" class="header__logotype">
        <img src="" data-src="https://i.ibb.co/VS0k7Nh/Logo.jpg" alt="Logotype">
      </a>
      <!-- Список навигации -->
      <nav>
        <ul  class="d-f ul-reset header__ul">
          <ItemLink  v-for="(item, ind) in nav" :key="ind" class="header__navigationItem" :item="item"/>
        </ul>
      </nav>
      <!-- кнопка "связаться" и кнопка валюты -->
      <nav class="ulVal">
        <ul class="d-f ul-reset  ulValUl">
          <li class="header__navigationRightBlock fw-bold c-pointer">Зв'язатися</li>
          <li class="header__navigationRightBlock header__lastChild"><span class="fw-bold c-pointer">UA</span>  <span class="c-pointer">EN</span></li>
        </ul>
      </nav>

    </div>
  </header>
</template>

<script>
  import ItemLink from './ItemLink'
export default {
 data(){
  return{
    nav:[
      {link:'', name:'Головна'},
      {link:'', name:'Про компанію'},
      {link:'', name:'Рослинництво'},
      {link:'', name:'Тваринництво'},
      {link:'', name:'Новини'},
      {link:'', name:'Контакти'},
    ]
  }
 },
 components:{
   ItemLink
 }
}
</script>

<style lang="less">
@import './src/assets/less/smart-grid.less';
@import './src/assets/less/mixins.less';
    .ulVal{
        .media(900px,{
            width: 100% !important;
        });
    }
    .ulValUl{
        .media(900px,{
            display: flex;
        justify-content: space-between;
        });
    }
  .header{
    /* margin-top: 30px; */
   
    &__logotype{
      position: relative;
      left: -20px;
      .media(700px,{
        left: 0;
       });
    }
    &__ul{
      padding-left: 0px;
      padding-right: 0px;
       .media(700px,{
        flex-wrap: wrap;
        .size(12);
        });
    }
    &__navigationItem{

      margin-left: 12px;
      margin-right: 12px;
      line-height: 120px;
      position: relative;
      .media(700px,{
        .size(5);
        line-height: 30px;
        text-align: center;
       });
      &:after{
        content:'';
        position: absolute;
        bottom: 0;
        width: 0%;
        left: 0;
        margin: 0;
        padding: 0;
        border:0px solid #D08C00;
        transition: width 0.5s;
      }
      &:hover:after{
        width: 100%;
        border:5px solid #D08C00;
      }
    }
    &__navigationRightBlock{
      padding-left: 24px;
      padding-right: 24px;
      border-left: 1px solid 	rgba(112,112,105,0.3);
      border-right: 1px solid rgba(112,112,105,0.3);;
      line-height: 120px;
    }
    &__lastChild{
      border-left: none;
    }
  }
</style>