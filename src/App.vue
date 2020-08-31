<template>
  <div id="app">
    <Header class="wrapper"/>
    <main>
      <section class="d-f">
        <Presentation :dataPresent="presentOne"/>
        <Presentation :dataPresent="presentTwo"/>
      </section>

      <section class="pt-200 pb-135 mapBackground">
        <div class="wrapper">
          <TextComponent  :text="presentThree"/>
        </div>
      </section>

      <SectionDescription :obj="obj"/>

      <SectionGrid :gridData="sectionGrid"/>

      <SectionVideo/>

      <SectionForm img="https://i.ibb.co/QQ26gfz/image.png"/>

      <SectionDescription :obj="obj2"/>

      <SectionGrid :gridData="sectionGrid"/>

      <SectionForm img="https://i.ibb.co/QFFdWGm/three-sunflowers-6-ZWQYG3.png"/>

      <section class="news">
          <div class="wrapper">
            <h2 class="news__h">Новини</h2>
            <div class="row">
              <NewsCard v-for="(objNews, i) in massNews" :objNews="objNews"  :key="i"/>
            </div>
          </div>
      </section>
    </main>
    
    <Footer/>
  </div>
</template>

<script>
import Header from './components/Header/Header';
import Presentation from './components/Presentation';
import TextComponent from './components/TextComponent';
import SectionDescription from './components/SectionDescription';
import SectionGrid from './components/SectionGrid';
import SectionVideo from './components/SectionVideo';
import SectionForm from './components/SectionForm';
import NewsCard from './components/NewsCard';
import Footer from './components/Footer';
export default {
  name: 'App',
  data(){
    return{
      // Данные обьекты написы без логической, смысловой нагрузкой, поскольку это тестовое задание, 1 страница без бизнес логики
      presentOne:{
        image:'https://i.ibb.co/fDnxp2J/1.jpg',
        headingText:'Тваринництво:вівчарні ферми',
        text:[
          'З 2018 року в Українській Асоціації Вівчарів. До 3 000 голів у 2020. Експорт мяса до Європи та Близького Сходу.',
        ],
        link:'Детальніше',
        positionText:'right',
        styleObject:{
          width:'350px',
          color:'white'
        }
      },
      presentTwo:{
        image:'https://i.ibb.co/Jk5vPK0/field-of-golden-wheat-PQHH5-BZ.jpg',
        headingText:'Тваринництво:вівчарні ферми',
        text:[
          'З 2018 року в Українській Асоціації Вівчарів. До 3 000 голів у 2020. Експорт мяса до Європи та Близького Сходу.'
        ],
        link:'Детальніше',
        positionText:'left',
        backgroundColor:'#DBB056',
        styleObject:{
          width:'350px',
          color:'white'
        }
      },
      presentThree:{
        image:'https://i.ibb.co/zX8pqWk/back.png',
        headingText:'Науково-виробниче Агропромислове',
        text:[
          'Науково-виробниче агропромислове підприємство «Ель Гаучо» знаходиться на Тернопільщині. Вже більше 10 років ми займаємося рослинництвом: вирощуємо сорти та гібриди актуальних культур для цього регіону.',
          'З кожним роком фермерське господарство розвивається в галузі рослинництва, робить акцент на інтенсивність технології з дотриманням максимальних врожаїв. '
        ],
        link:'Детальніше',
        styleObject:{
          width:'590px',
          color:'#500000'
        }
      },
      presentFour:{
        image:'https://i.ibb.co/zX8pqWk/back.png',
        headingText:'Тваринництво',
        text:[
          'Розведення вівців породи Мериноландшаф, яких привезли з Австрії. Ці тварини добре пристосовуються до різних кліматичних умов, проте для формування здорового організму їм потрібен комфорт.',
        ],
        link:'Детальніше',
        styleObject:{
          width:'430px',
          color:'#500000',
          marginBottom:'40px'
        }
      },
      descriptionIcon:{
        icon:'https://i.ibb.co/FBTGLLJ/sheep.png',
        textTop:'2500',
        textBottom:'голів'
      },
      obj:{
        backgroundSection:true,
        present:{
          image:'https://i.ibb.co/zX8pqWk/back.png',
          headingText:'Тваринництво',
          text:[
            'Розведення вівців породи Мериноландшаф, яких привезли з Австрії. Ці тварини добре пристосовуються до різних кліматичних умов, проте для формування здорового організму їм потрібен комфорт.',
          ],
          link:'Детальніше',
          styleObject:{
            width:'430px',
            color:'#500000',
            marginBottom:'40px'
          }
        },
        descriptionIcon:[
            {
                icon:'https://i.ibb.co/FBTGLLJ/sheep.png',
                textTop:'2500',
                textBottom:'голів'
            },
             {
                icon:'https://i.ibb.co/FBTGLLJ/sheep.png',
                textTop:'2500',
                textBottom:'голів'
            }
        ],
        descriptionText:[
            ' Європейський досвід і мрія про відродження вівчарства в Україні стали ключовими у виборі нової галузі господарства. Для розведення обрали вівців породи Мериноландшаф, яких привезли з Австрії. Ці тварини добре пристосовуються до різних кліматичних умов, проте для формування здорового організму їм потрібен комфорт. Тому ми збудували з екологічно чистих матеріалів дві сучасні ферми.,',
            'Просторі стайні, достатньо кисню для дихання та світла, постійний доступ до їжі – усе задля комфорту тварин! А отже – гарні умови для формування племінного генетичного матеріалу! Європейський досвід і мрія про відродження вівчарства в Україні стали ключовими у виборі нової галузі господарства. Для розведення обрали вівців породи Мериноландшаф, яких привезли з Австрії. Ці тварини добре пристосовуються до різних кліматичних умов, проте для формування здорового організму їм потрібен комфорт. Тому ми збудували з екологічно чистих матеріалів дві сучасні ферми. Просторі стайні, достатньо кисню для дихання та світла, постійний доступ до їжі – усе задля комфорту тварин! А отже – гарні умови для формування племінного генетичного матеріалу!'
        ]
      },
      obj2:{
        backgroundSection:true,
        present:{
          image:'https://i.ibb.co/zX8pqWk/back.png',
          headingText:'Рослинництво',
          text:[
            'Розведення вівців породи Мериноландшаф, яких привезли з Австрії. Ці тварини добре пристосовуються до різних кліматичних умов, проте для формування здорового організму їм потрібен комфорт.',
          ],
          link:'Детальніше',
          styleObject:{
            width:'430px',
            color:'#500000',
            marginBottom:'40px'
          }
        },
        descriptionIcon:[
            {
                icon:'https://i.ibb.co/FBTGLLJ/sheep.png',
                textTop:'Насіння',
                textBottom:'Завод з виробництва '
            },
             {
                icon:'https://i.ibb.co/FBTGLLJ/sheep.png',
                textTop:'10 років ',
                textBottom:'Рослинництва'
            }
        ],
        descriptionText:[
          'Науково-виробниче агропромислове підприємство «Ель Гаучо» знаходиться на Тернопільщині. Вже більше 10 років ми займаємося рослинництвом: вирощуємо сорти та гібриди актуальних культур для цього регіону. З кожним роком фермерське господарство розвивається в галузі рослинництва, робить акцент на інтенсивність технології з дотриманням максимальних врожаїв. Науково-виробниче агропромислове підприємство «Ель Гаучо» знаходиться на Тернопільщині. Вже більше 10 років ми займаємося рослинництвом: вирощуємо сорти та гібриди актуальних культур для цього регіону. З кожним роком фермерське господарство розвивається в галузі рослинництва, робить акцент на інтенсивність технології з дотриманням максимальних врожаїв. Науково-виробниче агропромислове підприємство «Ель Гаучо» знаходиться на Тернопільщині. Вже більше 10 років ми займаємося рослинництвом: вирощуємо сорти та гібриди актуальних культур для цього регіону. З кожним роком фермерське господарство розвивається в галузі рослинництва, робить акцент на інтенсивність технології з дотриманням максимальних врожаїв.'
        ]
      },
      massNews:[
        {
          img:'https://i.ibb.co/7ttLKnC/2.png',
          figcapture:'Серпень 02, 2020',
          h:'Триває будівництво другої ферми.',
          p:'рибатекст допоможе дизайнеру, верстальщику, вебмастеру сгенерувати декілька абзаців, більш мяких, ніж осміленого, текстових виробів на російській мові, а починаючи оратору відбивати важливих публікацій у домашніх умовах.',
          link:'#'
        },
        {
          img:'https://i.ibb.co/7ttLKnC/2.png',
          figcapture:'Серпень 02, 2020',
          h:'Триває будівництво другої ферми.',
          p:'рибатекст допоможе дизайнеру, верстальщику, вебмастеру сгенерувати декілька абзаців, більш мяких, ніж осміленого, текстових виробів на російській мові, а починаючи оратору відбивати важливих публікацій у домашніх умовах.',
          link:'#'
        },
        {
          img:'https://i.ibb.co/7ttLKnC/2.png',
          figcapture:'Серпень 02, 2020',
          h:'Триває будівництво другої ферми.',
          p:'рибатекст допоможе дизайнеру, верстальщику, вебмастеру сгенерувати декілька абзаців, більш мяких, ніж осміленого, текстових виробів на російській мові, а починаючи оратору відбивати важливих публікацій у домашніх умовах.',
          link:'#'
        }

      ],
      sectionGrid:{
        1:'https://i.ibb.co/28c8mW0/image.jpg',
        2:'https://i.ibb.co/xhvs2Rf/viber-2019-10-04-17-10-02.jpg',
        3:'https://i.ibb.co/RpCh1rJ/viber-2019-10-04-17-10-03.jpg',
        4:'https://i.ibb.co/zJ6KSJ7/image.jpg',
        5:'https://i.ibb.co/P1Rc1dZ/image.jpg',
        6:'https://i.ibb.co/HXBK4pr/95466242-2990125564389854-6308128161099939840-n.jpg'
      }
    }
  },
  components: {
    Header,
    Presentation,
    TextComponent,
    SectionDescription,
    SectionGrid,
    SectionVideo,
    SectionForm,
    NewsCard,
    Footer
  },
  methods:{
    lazyLoad(target){
    let observer = new IntersectionObserver((entries, observer)=>{
        entries.forEach(entry => {
          if(entry.isIntersecting){
            let img =  entry.target;
            if(entry.target.nodeName == 'IMG'){
              img.src = img.getAttribute('data-src');
            }
            if(entry.target.nodeName == 'DIV'){
              img.style.backgroundImage = `url(${img.getAttribute('data-src')})`
            }
            observer.unobserve(img)
          }
        });
    });
      observer.observe(target);
    }
  },
  mounted(){
    const targets = document.querySelectorAll('img');
    const sectionItem = document.querySelectorAll('.imageSection__item');
    const sectionVideo = document.querySelector('.sectionVideo__bgc');
    const sectionForm = document.querySelectorAll('.sectionForm__backGroundImage');
    targets.forEach(this.lazyLoad)
    sectionItem.forEach(this.lazyLoad)
    sectionForm.forEach(this.lazyLoad)
    this.lazyLoad(sectionVideo)
  }
}
</script>

<style lang="less">
  @import '../src/assets/less/smart-grid.less';
  @import '../src/assets/less/mixins.less';
  @import '../src/assets/less/setDefaults.less';
  @import '../src/assets/less/atomic.less';
  @import '../src/assets/less/global.less';
  
  /* General */
  #app{
    background-color: #FFFFFF;
    font-family: 'Gilroy';
    font-style: normal;
  }
.mapBackground{
  overflow: hidden;
  position: relative;
  border-bottom: 1px solid #707070;
  &:after{
  content:'';
  position: absolute;
  overflow: hidden;
  background-image: url('https://i.ibb.co/9vN91BZ/599.webp');
  background-size: contain;
  background-repeat: no-repeat;
  top: -303px;
  right: -232px;
  width: 926px;
  height: 814px;
  }
}
.descriptionWrapper{
  .size(3);
}
.news{
  padding-top: 103px;
  padding-bottom: 289px;
  background-image: url(https://i.ibb.co/28sLLyc/728.webp);
  background-repeat: no-repeat;
  background-position: 180%  850%;

  &__h{
    margin-bottom: 46px;
    font-size: 50px;
    font-weight: bold;
    color: #421100;
  }
}

</style>
