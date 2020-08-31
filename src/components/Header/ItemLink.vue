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

<style lang="less" scoped>
    .link{
        text-decoration: none;
        color: black;
    }
</style>