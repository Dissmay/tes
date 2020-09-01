<template>
<!-- компонент (секция) принимает обьект -->
  <section :class="obj.backgroundSection ? 'pb-70 backgroundHourse' : 'pb-70'">
        <div>
            <div class="wrapper sectionDescription__wrapper  pt-130 pb-30 d-f jc-between ai-center">

                <TextComponent :text="obj.present"/>

                <div class="d-f jc-between descriptionWrapper">
                    <DescriptionIcon :dataIcon="desc" v-for="(desc, i) in obj.descriptionIcon" :key="i"/>
                </div>

            </div>
            <div class="wrapper">
                <p class="desctiprionText mb-33" v-for="(text, i) in obj.descriptionText" :key="i">
                {{text}}
                </p>
            </div>
          
        </div>
      </section>
</template>

<script>
import TextComponent from './TextComponent';
import DescriptionIcon from './DescriptionIcon'
export default {
    props:['obj'],
    data(){
        return{
            
        }
    },
    components:{
        TextComponent,
        DescriptionIcon
    }

}
</script>

<style lang="less" scoped>
 @import './src/assets/less/smart-grid.less';
  @import './src/assets/less/mixins.less';
  .sectionDescription__wrapper{
      .media(900px,{
          display:block;
      });
  }
    .desctiprionText{
        font-size: 18px;
        color:#421100;
        font-family: 'Girloy-Medium';

        line-height: 25px;
        &__top{
           
        
        }
        &__bottom{
            
        }
    }
    .descriptionWrapper{
        .shift-right(0.8);
        .media(900px,{
            padding-top: 40px;
            width: 100%;
        });
    }
     .backgroundHourse{
        position: relative;
        background-image: url('https://i.ibb.co/VYWvqBC/background-Section.png');
        background-position: -80% -60%;
        background-repeat: no-repeat;
    }
</style>