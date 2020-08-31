<template>
    <section class="grid-container">
      <!-- секция принимает обьект, компонент статический, обьект принимает только 6 параметров.  -->
      <div  :class="'imageSection__item item'+i" v-for="(item, i) in gridData" :key="i" 
             :data-src="item"/>
    </section>
</template>

<script>
export default {
  props:['gridData']
}
</script>

<style lang="less" scoped>
.imageSection{
    &__item{
        background-repeat: no-repeat;
        background-size: cover;
    }
}
.grid-container {
  display: grid;
  height:100%;
  grid-template-columns: 1fr 1fr 1fr 1fr;
  grid-template-rows: 0.5fr 1.5fr;
  gap: 18px 15px;
  grid-template-areas: "item1 item3 item4 item6" "item2 item3 item5 item6";
  padding-bottom: 20px;
}
.item1{
  height: 285px;
  grid-area: item1;
}
.item2{
  grid-area: item2;
  height: 495px;
}
.item3{
  grid-area: item3;
}
.item4{
  grid-area: item4;
}
.item5{
  grid-area: item5;

}
.item6{
  background-repeat: no-repeat;
  background-size: cover;
  grid-area: item6;
}
</style>