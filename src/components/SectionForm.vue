<template>
  <section class="sectionForm">
      <!-- компонент формы, принимает изображение -->
      <div class="sectionForm__backGroundImage" :data-src="img"></div>
      <div class="wrapper sectionForm__div d-f pt-150 pb-150">
          <div class="sectionForm__wrapperText">
              <h2>
                  Виникли 
              </h2>
              <p>
                  Залиште свій номер телефону, ми обов'язково зателефонуємо.
              </p>
          </div>
          <form action="" class=" form">
                <input class="form__input1" type="text" placeholder="Ваше имя">
                <input class="form__input2" type="text" placeholder="Ваше имя">
                <input class="form__input3" type="text" placeholder="Ваше имя">
                <button class="button">Відправити -></button>
          </form>
      </div>
  </section>
</template>

<script>
export default {
    props:['img']
}
</script>

<style lang="less">
  @import './src/assets/less/smart-grid.less';
  @import './src/assets/less/mixins.less';
    .sectionForm{
        background-color: #F2F2F2;
        background-image: url(https://i.ibb.co/dbLJHmj/3.png);
        background-repeat: no-repeat;
        position: relative;
        &__backGroundImage{
            position: absolute;
            background-size: cover;
            height: 100%;
            width: 30%;
            background-repeat: no-repeat;
            bottom: 0;
            right: 0;
        }
        &__div{
            color:#421100;
            justify-content: space-between;
            .media(900px,{
                display: block !important; 
            });
        }

        h2{
            font-size: 50px;
            font-family: 'Girloy-Bold';
            line-height: 45px;
            margin-bottom: 30px;
        }
        p{
            font-size: 18px;
            font-family: 'Girloy-Medium';
            line-height: 25px;
        }
        &__wrapperText{
            .shift-left(-0.7);
            .media(1250px,{
                .shift-left(0);
            })
        }
    }
    
    .form{
        .shift-right(2);
         justify-items: end;
        input{
            width: 183px;
            border:none;
            border-bottom: 1px solid black;
            line-height: 45px;
            margin-bottom: 45px;
            background-color: #F2F2F2;
            .media(450px,{
                width:100px;
                justify-items: start;
                .shift-right(0);
            });
        }
        button{
            height: 70px;
            width: 183px;
            background-color:transparent;
            border:none;
            font-size: 20px;
            color: #D08C00;
            font-weight: bold;
            text-align: left;
            cursor:pointer;
        }
        display: grid;
        grid-template-columns: 183px 183px;
        gap: 10px 56px;
        grid-template-areas: "input1 input2" "input3 button";
         .media(450px,{
                width:100px;
                justify-items: start;
                grid-template-columns: 100px 100px;
                .shift-right(0);
                gap:10px 10px;
            });
        &__input1{
            grid-area: input1;
        }
        &__input2{
            grid-area: input2;
        }
        &__input3{
            grid-area: input3;
        }
        &__button{
            grid-area: button;
        }
    }
</style>