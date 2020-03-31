<template>
    <view>
myListsss
<text v-for="(item,index) in opstion" :key='index'></text>
    </view>
</template>

<script>
import reduction from "../../../static/reduction";
    export default {
        props: ['name'],
       onReady () {
           console.log(this.name)
           this.opstion=reduction[this.name]
       },
       data() {
           return {
               opstion: []
           }
       },
       mounted () {
			console.log(8888)
		},
    }
</script>

<style lang="scss" scoped>

</style>