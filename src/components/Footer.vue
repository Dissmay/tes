<template>
    <footer class="footer">
        <div class="wrapper">
            <div class="d-f row align-items-center footer__top">
                <div class="footer__itemSizeLogo">
                    <div>
                        <img data-src="https://i.ibb.co/fX078vP/616.png" alt="">
                    </div>
                    <p class="white-text">
                        Науково-виробниче агропромислове підприємство «Ель Гаучо» більше 10 років займаємося рослинництвом: вирощуємо сорти та гібриди актуальних культур для цього регіону.
                    </p>
                </div>
                <div class="footer__itemSizeSections white-text ">
                    <h3 class="footer__hUl">Розділи сайту:</h3>
                    <ul class="d-f ul-reset row footer__ul">
                        <li class="footer__li">Головна</li>
                        <li class="footer__li">Про компанію</li>
                        <li class="footer__li">Новини</li>
                        <li class="footer__li">Рослинництво </li>
                        <li class="footer__li">Тваринництво</li>
                        <li class="footer__li">Контакти</li>
                    </ul>
                </div>
                <div class="footer__itemSizeContact white-text">
                    <h3 class="footer__hUl">Контакти:</h3>
                    <ul class="ul-reset  footer__ul">
                        <li class="footer__contact_li">Тернопільська обл., Залішицький р-н, с. Товсте</li>
                        <li class="footer__contact_li">+38 (067) 401-49-48</li>
                        <li class="footer__contact_li">m.volchenko@agrosem.ua</li>
                    </ul>
                </div>
            </div>
            <ul class="row align-items-center pt-35 footer__bot white-text ul-reset">
                <li>
                    Ель Гаучо © 2020. Всі права захищені.
                </li>
                <li class="ta-c">
                    Політика конфіденційності
                </li>
                <li>
                    <ul class=" row ul-reset footer__bot__ulSocial">
                        <li class="footer__bot__liSocial"><a class="white-text" href="#"><i class="fa fa-facebook" aria-hidden="true"></i></a></li>
                        <li class="footer__bot__liSocial"><a class="white-text" href="#"><i class="fa fa-instagram" aria-hidden="true"></i></a></li>
                        <li class="footer__bot__liSocial"><a class="white-text" href="#"><i class="fa fa-youtube-play" aria-hidden="true"></i></a></li>
                        <li class="footer__bot__liSocial"><a class="white-text" href="#"><i class="fa fa-telegram" aria-hidden="true"></i></a></li>
                    </ul>
                </li>
                <li class="d-f liLogo">
                    <p class="ta-r">Розробка сайту</p>
                    <img data-src="https://i.ibb.co/bRnX2Xp/themoon-white-logo.png" alt="">
                </li>
            </ul>
        </div>
    </footer>
</template>

<script>
export default {

}
</script>

<style lang="less">
  @import './src/assets/less/smart-grid.less';
  @import './src/assets/less/mixins.less';
    .footer{
        background-color: #421100;
        padding-top: 95px;
        padding-bottom: 52px;
        &__top{
            padding-bottom: 50px;
            border-bottom: 1px solid #D08C00;
            justify-content: space-between;
            div{
                .media(900px,{
                    .size(6);
                    margin-bottom: 30px;
                });
                 .media(600px,{
                    .size(12);
                    margin-bottom: 10px;
                });
            }
        }
        &__itemSizeLogo{
            .col();
            .size(3);
            margin-left: 0;
            p{
                font-size: 16px;
                font-family: 'Arial';
            }
        }
        &__itemSizeSections{
            .col();
            .size(4);
        }
        &__hUl{
            color: #D08C00;
            font-family: "Arial";
            font-size: 16px;
            line-height: 18px;
            margin-bottom: 10px;
            margin-top: 5px;
        }
        &__ul{
            margin-top: 10px;
        }
        &__li{
            .col();
            .size(6);
            font-size: 18px;
            font-family: 'Arial';
            line-height: 39px;
            color: #FFFFFF;
        }
        &__contact_li{
        }
        &__itemSizeContact{
            line-height: 39px;
            flex-direction: column;
            justify-content: flex-end;
            align-items: flex-end;
        }
        &__bot{
            justify-content: space-between;
            .media(700px,{
                margin-left: 30px !important;
                margin-right: 30px !important;
            });
            li{
                font-size: 14px;
            
            }
            &__ulSocial{
               
            }
            &__liSocial{
                .col();
                .size(3);
            }
        }
    }
    .liLogo{
        justify-content: flex-end;
        align-content: flex-end;
        p{
            margin-right: 30px;
            align-items: flex-end;
            align-self: flex-end;
            line-height: 18px;
        }
        img{
        }
    }

</style>