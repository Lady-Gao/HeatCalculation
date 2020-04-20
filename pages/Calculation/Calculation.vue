<template>
    <view class='calculation'>
      <view class='m10'>
           <span>性别：      </span> 
                 <label class="radio" @click='radioChange'><radio value="nan" :checked="sex" />男</label>
                <label class="radio" @click='radioChange'><radio value="nv" :checked="!sex" />女</label>
            </view>
        <view class='m10'>
            <span>年龄：     </span>
            <input placeholder-style="color:rgb(202, 187, 187)" placeholder='25' :value='age' type='number' @input="ageInput"/>
             </view>
        <view class='m10'>
            <span>体重/kg：     </span>
            <input placeholder-style="color:rgb(202, 187, 187)" placeholder='45kg' :value='kg' type="number" @input="kgInput"/>
             </view>
        <view class='m10'>
            <span>身高：     </span>
           <input placeholder-style="color:rgb(202, 187, 187)" placeholder='160cm' :value='height' type='number' @input="heightInput"/>
             </view>
           <view class='m10 waring' v-if='waring'>
               <text>请输入正确的信息</text>
           </view>
             <button class='total' @click='seeCalorie'>卡路里 : {{total?total.toFixed(2):''}}</button>
   <icon type="info" size="26" class='info' @click='goIndex'/>
    </view>
</template>

<script>
    export default {
        data() {
            return {
                sex: true,
                age:null,
                kg:null,
                height:null,
                total:0,
                waring:false
            }
        },
       
        methods: {
            radioChange() {
                this.sex=!this.sex
            },
            ageInput(event) {
                this.age = event.target.value
            },
            heightInput(event) {
                this.height = event.target.value
            },
            kgInput(event) {
                this.kg = event.target.value
            },
            seeCalorie(){
                if(Number(this.kg)&&Number(this.height )&&Number(this.age)){
                    //男
                    if(this.sex){
                        this.total=66 + 1.38*this.kg + 5*this.height -6.8 *this.age
                    }else{
                        this.total=655 + 9.6*this.kg + 1.9*this.height -4.7*this.age
                    }
                   
                }
            },
           goIndex(){
               console.log(8)
               uni.navigateTo({
    url: '/pages/index/index'
});
           }
        },
    }
</script>

<style scoped>

.total{
    position: absolute;
    bottom: 10%;
    width: 60%;
    left: 20%;
    color:rgb(235, 167, 20);
}
.info{
     position: absolute;
    bottom: 11%;
    right: 8%;
}
.m10{
     margin: 10px;
     height: 60px;
     display: flex;
     justify-content: space-between;
     align-items: center;
}
.waring{
    color: brown;
}

</style>