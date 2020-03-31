<template>
	<view class='fat' >
	

		<view class='m50'>
				<view  class='backicon' v-if='opstion.length' @click='closeList'>一</view>
			<view class='fiedList' v-if='opstion.length'>
				<div class='Listbutton'  size="mini" v-for="(item,index) in opstion" :key='index' @click='pushItem(item)'
				:style='{"background":listItemBG(item)}'
				>
					{{item.type}}  
					<text style='color:#DDAA00'>{{item.value}}</text>
				</div>
			</view>
			<view class="container">
				<view   @click='setName("Fruits")'>
					<span :class='name=="Fruits"?"choseName":"otherName"' >水果 </span>
					<span class='span'>至少两份</span>
					<span class='hotspan'>热量：<text style='color:#DDAA00'>100</text>千卡/份</span>
				</view>
				<view class='buttonList'>
					<button class='bottonItem'  @click.native='popItem("Fruits",item)'    size="mini" v-for="item in Fruits" :key='item'>{{item.type}}
						<icon class='closeIcon' size='16'    type="cancel"></icon>
					</button>
					
				</view>
			</view>

			<view class="container" >
				<view @click='setName("meat")' >
					<span :class='name=="meat"?"choseName":"otherName"'>肉类 </span>
					<span class='span'>只限一份</span>
					<span class='hotspan'>热量：<text style='color:#DDAA00'>200</text>千卡/份</span>
				</view>
				<view class='buttonList'>
					<button class='bottonItem' @click='popItem("meat",item)' size="mini" v-for="item in meat" :key='item'>{{item.type}}
						<icon class='closeIcon' size='16'   type="cancel"  ></icon>
					</button>
					
				</view>
		    </view>

			<view class="container">
				<view   @click='setName("Nut")' >
					<span :class='name=="Nut"?"choseName":"otherName"'>坚果 </span>
					<span class='span'>只限两份</span>
						<span class='hotspan'>热量：<text style='color:#DDAA00'>50</text>千卡/份</span>
				</view>
				<view class='buttonList'>
					<button class='bottonItem'  @click='popItem("Nut",item)' size="mini" v-for="item in Nut" :key='item'>{{item.type}}
						<icon class='closeIcon' size='16' v-if='Nut.length' type="cancel" ></icon>
					</button>
					
				</view>
			</view>

			<view class="container" >
				<view  @click='setName("StapleFoodA")'>
					<span :class='name=="StapleFoodA"?"choseName":"otherName"'>A类主食 </span>
						<span class='hotspan'>热量：<text style='color:#DDAA00'>350</text>千卡/份</span>
				</view>
				<view class='buttonList'>
					<button class='bottonItem' @click='popItem("StapleFoodA",item)'  size="mini" v-for="item in StapleFoodA" :key='item'>{{item.type}}
						<icon class='closeIcon' size='16'  type="cancel"  ></icon>
					</button>
					
				</view>
			</view>

			<view class="container">
				<view   @click='setName("StapleFoodB")'>
					<span :class='name=="StapleFoodB"?"choseName":"otherName"'>B类主食 </span>
					<span class='span'>至少两份</span>
						<span class='hotspan'>热量：<text style='color:#DDAA00'>150</text>千卡/份</span>
				</view>
				<view class='buttonList'>
					<button class='bottonItem'  @click='popItem("StapleFoodB",item)' size="mini" v-for="item in StapleFoodB" :key='item'>{{item.type}}
						<icon class='closeIcon' size='16'   type="cancel" ></icon>
					</button>
					
				</view>
			</view>

			<view class="container" >
				<view  @click='setName("egg")'>
					<span :class='name=="egg"?"choseName":"otherName"'>蛋类 </span>
					<span class='span'>至少两份</span>
						<span class='hotspan'>热量：<text style='color:#DDAA00'>100</text>千卡/份</span>
				</view>
				<view class='buttonList'>
					<button class='bottonItem'  @click='popItem("egg",item)' size="mini" v-for="item in egg" :key='item'>{{item.type}}
						<icon class='closeIcon' size='16'   type="cancel" ></icon>
					</button>
					
				</view>
			</view>

			<view class="container">
					<view  @click='setName("milk")' >
					<span :class='name=="milk"?"choseName":"otherName"'>奶类 </span>
						<span class='hotspan'>热量：<text style='color:#DDAA00'>100</text>千卡/份</span>
				</view>
				<view class='buttonList'>
					<button class='bottonItem'  @click='popItem("milk",item)' size="mini" v-for="item in milk" :key='item'>{{item.type}}
						<icon class='closeIcon' size='16'  type="cancel" ></icon>
					</button>
					
				</view>
			</view>

			<view class="container" >
				<view  @click='setName("oli")'>
					<span :class='name=="oli"?"choseName":"otherName"'>植物油 </span>
					<span class='span'>只限三份</span>
						<span class='hotspan'>热量：<text style='color:#DDAA00'>50</text>千卡/份</span>
				</view>
				<view class='buttonList'>
					<button class='bottonItem'  @click='popItem("oli",item)' size="mini" v-for="item in oli" :key='item'>{{item.type}}
						<icon class='closeIcon' size='16'  type="cancel" ></icon>
					</button>
					
				</view>
			</view>

			<view class="container">
				<view   @click='setName("PeasBeans")'>
					<span :class='name=="PeasBeans"?"choseName":"otherName"'>豆类 </span>
					<span class='span'>只限三份</span>
						<span class='hotspan'>热量：<text style='color:#DDAA00'>50</text>千卡/份</span>
				</view>
				<view class='buttonList'>
					<button class='bottonItem' @click='popItem("PeasBeans",item)'  size="mini" v-for="item in PeasBeans" :key='item'>{{item.type}}
						<icon class='closeIcon' size='16'  type="cancel"  ></icon>
					</button>
					
				</view>
			</view>
		
			<view class="container">
				<view   @click='setName("Vegetables")'>
					<span :class='name=="Vegetables"?"choseName":"otherName"'>蔬菜 </span>
					<span class='span'>至少三份</span>
						<span class='hotspan'>热量：<text style='color:#DDAA00'>50</text>千卡/份</span>
				</view>
				<view class='buttonList'>
					<button class='bottonItem'  @click='popItem("Vegetables",item)' size="mini" v-for="item in Vegetables" :key='item'>{{item.type}}
						<icon class='closeIcon' size='16'   type="cancel" ></icon>
					</button>
					
				</view>
			</view>
	 
			<view class="container" >
				<view  @click='setName("Special")'>
					<span :class='name=="Special"?"choseName":"otherName"'>特殊类 </span>
						<span class='hotspan'>热量：<text style='color:#DDAA00'>800</text>千卡/份</span>
				</view>
				<view class='buttonList'>
					<button class='bottonItem'  @click='popItem("Special",item)' size="mini" v-for="item in Special" :key='item'>{{item.type}}
						<icon class='closeIcon' size='16'  type="cancel" ></icon>
					</button>
					
				</view>
			</view>
		</view>


		
	
	
	<button  class='allnum' @click="getTotal">合计：{{Total}}</button>
		
	</view>
</template>

<script>
	export default {
	
		data() {
			return {
				name:'',
				Fruits: [],
				meat: [],
				Nut: [],
				StapleFoodA: [],
				StapleFoodB: [],
				egg: [],
				milk: [],
				PeasBeans: [],
				Vegetables: [],
				Special: [],
				oli: [],
				opstion:[],
				Total:'',
				nowArr:[]
			}
		},
		mounted () {
			
		},
		computed: {
			
		},
		methods: {
			//设置右侧列表 
			setName(val){
				this.name=val
				this.opstion=reduction[val]
				this.nowArr=this[this.name]
			},
			//添加一项
			pushItem(item){
				this[this.name].push(item)
				this.getTotal()
			},
			//删除一项
			popItem(key,item){
				let index=this[key].indexOf(item)
				this[key].splice(index,1)
				this.getTotal()
			},
			//关闭右侧列表
			closeList(){
				this.opstion=[]
				this.name=''
			},
			listItemBG(item){
				return this[this.name].indexOf(item)==-1?'#fff':'#eee'
			},
			getTotal(){
				let Fruits=0,meat=0,Nut=0,StapleFoodA=0,StapleFoodB=0,egg=0,milk=0,PeasBeans=0,Vegetables=0,Special=0,oli=0	;
				// 	this.Fruits.map(item=>{
				// 		Fruits+=item.value
				// 	})
				// 	this.meat.map(item=>{
				// 		meat+=item.value
				// 	})
				// 	this.Nut.map(item=>{
				// 		Nut+=item.value
				// 	})
				// 	this.StapleFoodA.map(item=>{
				// 		StapleFoodA+=item.value
				// 		console.log(item.value,StapleFoodA)
				// 	})
				// 	this.StapleFoodB.map(item=>{
				// 		StapleFoodB+=item.value
				// 	})
				// 	this.egg.map(item=>{
				// 		egg+=item.value
				// 	})
				// 	this.milk.map(item=>{
				// 		milk+=item.value
				// 	})
				// 	this.PeasBeans.map(item=>{
				// 		PeasBeans+=item.value
				// 	})
				// 	this.Vegetables.map(item=>{
				// 		Vegetables+=item.value
				// 	})
				// 	this.Special.map(item=>{
				// 		Special+=item.value
				// 	})
				// 	this.oli.map(item=>{
				// 		oli+=item.value
				// 	})
				Fruits=this.Fruits.length*100
				meat=this.meat.length*200
				Nut=this.Nut.length*50
				StapleFoodA=this.StapleFoodA.length*300
				StapleFoodB=this.StapleFoodB.length*150
				egg=this.egg.length*100
				milk=this.milk.length*100
				oli=this.oli.length*50
				PeasBeans=this.PeasBeans.length*50
				Vegetables=this.Vegetables.length*50
				Special=this.Special.length*800
					this.Total=Fruits+meat+Nut+StapleFoodA+StapleFoodB+egg+milk+PeasBeans+Vegetables+Special+oli
				}
		}
	}
var reduction ={
   Fruits : [
     {type:'哈密瓜',value:400},
    {type:'苹果',value: 250},
    {type:'甜瓜',value: 400},
    {type:'西瓜',value: 500},
    {type:'梨',value: 250},
    {type:'桃',value: 250},
    {type:'青梅',value: 300},
    {type:'李子',value: 200},
    {type:'布朗',value: 250},
    {type:'杏',value: 200},
    {type:'鲜西梅',value: 300},
    {type:'樱桃',value: 250},
    {type:'火龙果',value: 250},
    {type:'葡萄',value: 250},
    {type:'山楂',value: 100},
    {type:'桑葚',value: 150},
    {type:'无花果',value: 150},
    {type:'草莓',value: 250},
    {type:'猕猴桃',value: 150},
    {type:'橙子',value: 250},
    {type:'冬枣',value: 100},
    {type:'柑橘',value: 250},
    {type:'石榴',value: 250},
    {type:'金桔',value: 200},
    {type:'柿子',value: 150},
    {type:'柚子',value: 200},
    {type:'茘枝',value: 150},
    {type:'波萝',value: 200},
    {type:'菠萝蜜',value: 100},
    {type:'番石榴',value: 150},
    {type:'人参果',value: 100},
    {type:'鲜桂圆',value: 200},
    {type:'芒果',value: 350},
    {type:'木瓜',value: 250},
    {type:'香蕉',value: 150},
    {type:'杨梅',value: 300},
    {type:'海棠果',value: 150},
    {type:'杨桃',value: 300},
    {type:'刺梨',value: 150},
    {type:'枇杷',value: 350},
    {type:'红毛丹',value: 150},
    {type:'白兰瓜',value: 600},
    {type:'山竹',value: 500},
 ]
   ,meat :[
     {type:'鲨鱼',value: 250},
     {type:'纯瘦牛肉',value: 150},
     {type:'鲈鱼',value: 300},
     {type:'羊里脊',value: 150},
     {type:'绸鱼',value: 300},
     {type:'兔肉',value: 150},
     {type:'鳕鱼段',value: 200},
     {type:'鸡胸脯',value: 150},
     {type:'带鱼段',value: 150},
     {type:'鸡/鸭胗',value: 150},
     {type:'对虾',value: 350},
     {type:'整乌骨鸡',value: 350},
     {type:'河虾',value: 250},
     {type:'鸭胸肉',value: 200},
     {type:'海虾',value: 450},
     {type:'火鸡胸肉',value: 150},
     {type:'基围虾',value: 300},
     {type:'纯瘦驴肉',value: 250},
     {type:'海蟹',value: 350},
     {type:'猪 / 鸭血',value: 300},
     {type:'河蟹',value: 400},
     {type:'鲤鱼',value: 300},
     {type:'鲍鱼',value: 350},
     {type:'罗非鱼',value: 350},
     {type:'蛏子',value: 800},
     {type:'草鱼',value: 300},
     {type:'蛤蜊',value: 800},
     {type:'鲇鱼',value: 250},
     {type:'扇贝',value: 800},
     {type:'鲫鱼',value: 300},
     {type:'螺蛳',value: 800},
     {type:'黄花鱼',value: 350},
     {type:'田螺',value: 1200},
     {type:'沙丁鱼',value: 350},
     {type:'鲜海参',value: 200},
     {type:'鲅鱼',value: 150},
     {type:'墨鱼',value: 200},
     {type:'比目鱼',value: 200},
     {type:'鱿鱼',value: 200},
     {type:'大马哈鱼',value: 1},
     {type:'生蚝',value: 850},
 ]
   ,Nut :[ 
    {type:"核桃仁",value: 10},
    {type:"山核桃仁",value: 10},
    {type:"炒松子",value: 25},
    {type:"杏仁",value: 10},
    {type:"腰果",value: 10},
    {type:"炒棒子",value: 40},
    {type:"花生仁",value: 10},
    {type:"葵花籽仁",value: 10},
    {type:"南瓜子",value: 15},
    {type:"西瓜子",value: 20},
    {type:"熟栗子",value: 25},
    {type:"芝麻",value: 10},
    {type:"开心果",value: 10},
 ]
   ,StapleFoodA : [
     {type:'意面',value:    85},
     {type:'燕麦片',value:    85},
     {type:'干切面',value:    85},
     {type:'全麦面包',value:    100},
     {type:'煮粥杂米',value:    85},
     {type:'米粉',value:    85},
     {type:'白面粉',value:    85},
     {type:'大米',value:    85},
     {type:'小米',value:    85},
     {type:'荞麦',value:    85},
     {type:'慧米',value:    85},
     {type:'粉丝',value:    85},
     {type:'粉条',value:    85},
 ]
   ,StapleFoodB : [
    {type:'糙米饭',value:    100},
    {type:'生红薯',value:    100},
    {type:'生鲜玉米(带芯)',value:    250},
    {type:'30克玉米精煮粥',value:    100},
    {type:'燕麦片',value:    40},
    {type:'全麦面包',value:    50},
   
 ]
   ,egg:[
   {type:'鸡蛋',value:   1},
   {type:'蛋清',value: 4},
 ]
   ,milk : [
     {type:'全脂牛奶',value:    150},
     {type:'酸奶',value:    100},
     {type:'脱脂奶',value:    300},
 ]
   ,oli : [
     {type:'橄榄油',value:    5},
     {type:'亚麻籽油',value:    5},
     {type:'葵花籽油',value:    5},
     {type:'大豆油',value:    5},
     {type:'花生油',value:    5},
     {type:'麦胚油',value:    5},
     {type:'菜籽油',value:    5},
 ]
   ,PeasBeans :[
    {type:'黄豆',value:   1},
    {type:'绿豆',value:   1},
    {type:'红豆',value:   1},
    {type:'花豆',value:   1},
    {type:'蚕豆',value:   1},
    {type:'扁豆',value:   1},
    {type:'鹰嘴豆',value:   1},
    {type:'北豆腐',value:   5},
    {type:'南豆腐',value:   10},
    {type:'豆浆',value:300},
 ] 
   ,Vegetables : [
  {type:'小白菜',value:   250},
  {type:'猴头菇',value:   200},
  {type:'白萝卜',value:   200},
  {type:'油菜',value:   200},
  {type:'鲜菇',value:   200},
  {type:'卞萝卜',value:   200},
  {type:'甘蓝',value:   200},
  {type:'干木耳',value:   20},
  {type:'水萝卜',value:   250},
  {type:'菜花',value:   250},
  {type:'口蘑',value:   200},
  {type:'荷兰豆',value:   150},
  {type:'雪菜',value:   200},
  {type:'香菇',value:   200},
  {type:'绿豆芽',value:   250},
  {type:'芥蓝',value:   250},
  {type:'杏鲍菇',value:   150},
  {type:'黄豆芽',value:   100},
  {type:'菠菜',value:   200},
  {type:'胡萝卜',value:   100},
  {type:'茄子',value:   200},
  {type:'芹菜茎',value:   250},
  {type:'豆角',value:   100},
  {type:'西红柿',value:   200},
  {type:'芹菜叶',value:   200},
  {type:'四季豆',value:   100},
  {type:'甜椒',value:   200},
  {type:'生菜',value:   350},
  {type:'豌豆苗',value:   150},
  {type:'菜瓜',value:   300},
  {type:'苋菜',value:   200},
  {type:'秋葵',value:   300},
  {type:'冬瓜',value:   500},
  {type:'苘蒿',value:   250},
  {type:'蒜苗',value:   150},
  {type:'佛手瓜',value:   250},
  {type:'茴香',value:   200},
  {type:'蒜苔',value:   100},
  {type:'西葫芦',value:   350},
  {type:'荠菜',value:   200},
  {type:'洋葱',value:   150},
  {type:'黄瓜',value:   300},
  {type:'莴苣',value:   500},
  {type:'韭苔',value:   150},
  {type:'苦瓜',value:   250},
  {type:'空心菜',value:   250},
  {type:'西蓝花',value:   150},
  {type:'南瓜',value:   250},
  {type:'竹笋',value:   350},
  {type:'青萝卜缨',value:   150},
  {type:'丝瓜',value:   200},
  {type:'春笋',value:   350},
  {type:'苦菜',value:   100},
  {type:'蒜黄',value:   200},
  {type:'芦笋',value:   200},
  {type:'冬笋',value:   250},
  {type:'韭菜',value:   200},
  {type:'菱白',value:   250},
  {type:'金针菇',value:   150},
  {type:'韭黄',value:   200},
  {type:'草菇',value:   200},
  {type:'鲜海带',value:   400},
  {type:'大白菜',value:   250},
  {type:'藕',value:   100},
  {type:'鲜百合',value:   50},

 ]
   ,motion : {
    
 },
   Special : [
     {type:'啤酒(100/克)',value: 50},
     {type:'红酒(100/克)',value: 100},
     {type:'白酒(100/克)',value: 350},
     {type:'小汉堡/个',value: 400},
     {type:'中汉堡/个',value: 600},
     {type:'大汉堡/个',value: 800},
     {type:'普通薯条/份',value: 200},
     {type:'大薯条/份',value: 300},
     {type:'小鸡米花/份',value: 400},
     {type:'大鸡米花/份',value: 600},
     {type:'普通热狗/份',value: 300},
     {type:'普通奶昔/份',value: 600},
     {type:'大奶昔/份',value: 900},
     {type:'圣代/份',value: 550},
     {type:'小甜筒/份',value: 200},
 ]
}

</script>

<style >
	.fat{
		font-size: 12;
	}
	.allnum{
		position: fixed;
		bottom: 0;
		width: 100%;
		background-color: #007AFF;
		z-index: 9;
		font-weight: bold;
		color: #fff;
	}
	.m50{
		margin-top: 10px;
		position: absolute;
		height: 90%;
		width:100%;
		overflow: scroll;
		
	}
	.otherName{
		font-weight: bold;
		color: #979292;
		font-size: 18px;
	}
	.choseName{
		font-weight: bold;
		color: #1a61e4;
		font-size: 20px;
	}
	.span{
		padding-left: 30px;
		font-size: 10;
		color: rgb(216, 210, 210);
	}
	.hotspan{
		float: right;
		color: rgb(182, 177, 177);
	}
	.container{
		padding-left: 10px;
		min-height:50px;
	}
	.buttonList{
		display: flex;
		flex-wrap: wrap;
		justify-content: start;
		margin: 10px;
	
	}
	.closeIcon{
		position: relative;
		right: -15px;
		top: -3px;

	}
	.bottonItem{
		background-color: rgb(235, 167, 20);
		margin: 5px;
		color: #fff;
	}
	.button{
		/* text-align: left; */
		width:100%;
		background-color:#fff;
		color: #706d6d;
	margin-top: 5px;
	}

	.fiedList{
		 position: fixed;
		 width: 35%;
		 overflow: scroll;
		 right: 0;
		 top:0;
		 max-height: 92%;
		 background-color: #fff;
		 z-index: 1;
		box-shadow: 0px 0px 20px #94ade0;
		border-radius: 10px;

	}
	.Listbutton{
		padding:10px ;
		color:rgb(145, 140, 140);
		border-bottom: 1px solid #eee;
		text-align: center;
	}
	.backicon{
		position: fixed;;
		left: 60%;
		top:0.8%;
		z-index: 2;
		background: #007AFF;
		width: 30px;
		height: 30px;
		border-radius: 50%;
		text-align: center;
		line-height: 30px;
		color: #fff;
	}
</style>
