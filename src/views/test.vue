<template>
  <div class="xx" ref="wrapper">
    <ul>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
        <li>123456</li>
    </ul>
  </div>
</template>

<script>
import BScroll from 'better-scroll'
export default {
    data() {
        return {
            bscorll:null
        }
    },
    mounted() {
        this.bscorll = new BScroll(this.$refs.wrapper)
    },
}
</script>

<style>
.xx {
    height: 200px;
    background-color: pink;
    overflow: hidden;
}
</style>