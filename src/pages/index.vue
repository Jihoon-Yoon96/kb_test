<template>
    <section class="sec01 reveal indexmain active animation" v-html="top"></section>

    <section class="sec02" v-html="section1"></section>

    <section class="sec03  line" v-html="section2"></section>

    <section class="sec04  line" v-html="section3"></section>

    <section class="sec05 line" v-html="section4"></section>

    <section class="sec06 line center" v-html="section5"></section>

    <section class="sec07 line center" v-html="section6"></section>

    <section class="sec08 " v-html="section7"></section>

    <section class="sec09 " v-html="section8"></section>

    <section class="affiliate" v-html="partners"></section>

    <section class="sns" v-html="sns"></section>
</template>

<script setup lang="ts">

let top: string = ''
let section1: string = ''
let section2: string = ''
let section3: string = ''
let section4: string = ''
let section5: string = ''
let section6: string = ''
let section7: string = ''
let section8: string = ''
let section9: string = ''
let section10: string = ''
let partners: string = ''
let sns: string = ''

const {data, pending, error, refresh} = await useFetch('http://125.131.88.58:8055/items/kb_main/1')
console.log(data)
if (data.value){
    top = data.value.data.top
    section1 = data.value.data.section1
    section2 = data.value.data.section2
    section3 = data.value.data.section3
    section4 = data.value.data.section4
    section5 = data.value.data.section5
    section6 = data.value.data.section6
    section7 = data.value.data.section7
    section8 = data.value.data.section8
    section9 = data.value.data.section9
    section10 = data.value.data.section10
    partners = data.value.data.partners
    sns = data.value.data.sns
}
else{
    console.log(error)
}

</script>

<style scoped>

</style>