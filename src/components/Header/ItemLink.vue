<template>
    <li>
        <a class="link" :href="item.link">{{item.name}}</a>
    </li>
</template>

<script>
export default {
    props:['item']
}
</script>

<style lang="less">
    .link{
        text-decoration: none;
         color: #421100;
        font-family: 'Gilroy-Medium';
        
    }
</style>