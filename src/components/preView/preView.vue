<template>
  <div v-if="showPreview">
	<div class="preView">
		<div class="covery"></div>
		<transition-group name='fade' tag="ul" class="imgs-wrapper" mode="out-in">		
			<li v-for="(item,index) in preView" class="common" v-show="index == preViewShowIndex" :key='item' :style="move">
				<img :src="item" >
			</li>
		</transition-group>
		<button class="prebtn btn" @click="preClick">上一页</button>
		<button class="backbtn btn" @click="backClick">下一页</button>
		<div class="closeBtn" @click="preViewClose">X</div>
	</div>
	<div class="payAlbum">
		<div class="item">
			<label for="uName">姓名：</label>
			<input type="text" name="uName" id="uName" placeholder="请输入收货人姓名">
		</div>
		<div class="item">
			<label for="uPhone">联系方式：</label>
			<input type="text" name="uPhone" id="uPhone" placeholder="请输入收货人手机号">
		</div>
		<div class="item">
			<label for="uAdress">收货地址：</label>
			<input type="text" name="uAdress" id="uAdress" placeholder="请输入收货地址">
		</div>
		<button @click="sendJson">一键打印</button>
	</div>
  </div>
</template>
<style lang="less">
.preView{
	position:fixed;
	top: 20%;
<<<<<<< HEAD
	left:5.5%;
=======
	left:0%;
>>>>>>> 864c52ad507faa7dcfc345c150a3b87465f0cad7
	width:70%;
	z-index:100;

}
.payAlbum{
	position: fixed;
	top: 0;
	right: 0;
	width: 30%;
	z-index: 100;
	background-color: #fff;
	height: 100%;
	.item{
		width: 70%;
		height: 100px;
	}
}
.covery{
	position: fixed;
	width: 100%;
	height: 100%;
	z-index: 99;
	background-color: rgba(0,0,0,0.5);
	left: 0;
	top: 0;
}
.btn{
	position: fixed;
	width: 50px;
	z-index: 100;
	color: #888;
	text-shadow: 0 1px 0 rgba(255,255,255, 0.8);
	text-decoration: none;
	text-align: center;
	padding: 8px 12px;
	font-size: 12px;
	font-weight: 700;
	font-family: helvetica, arial, sans-serif;
	border-radius: 4px;
	border: 1px solid #bcbcbc;
	-webkit-box-shadow: 0 1px 3px rgba(0,0,0,0.12);
	box-shadow: 0 1px 3px rgba(0,0,0,0.12);
	background-image: -webkit-linear-gradient(top, rgba(255,255,255,1) 0%,rgba(239,239,239,1) 60%,rgba(225,223,226,1) 100%);
	background-image: -moz-linear-gradient(top, rgba(255,255,255,1) 0%,rgba(239,239,239,1) 60%,rgba(225,223,226,1) 100%);
	background-image: -o-linear-gradient(top, rgba(255,255,255,1) 0%,rgba(239,239,239,1) 60%,rgba(225,223,226,1) 100%);
	background-image: -ms-linear-gradient(top, rgba(255,255,255,1) 0%,rgba(239,239,239,1) 60%,rgba(225,223,226,1) 100%);
	background-image: linear-gradient(top, rgba(255,255,255,1) 0%,rgba(239,239,239,1) 60%,rgba(225,223,226,1) 100%);
	
}
.btn:hover{
	cursor:pointer; 
	-webkit-box-shadow:0 0 10px rgba(0, 204, 204, .5);  
  	-moz-box-shadow:0 0 10px rgba(0, 204, 204, .5);  
 	 box-shadow:0 0 10px rgba(0, 204, 204, .5);  
}
.closeBtn{
	position: fixed;
	width: 30px;
	height: 30px;
	border-radius: 30px;
	z-index: 100;
	top: 20%;
	left: 55%;
	font-size: 12px;
	background-color: #ccc;
	line-height: 30px;
}
.closeBtn:hover{
	cursor:pointer; 
	-webkit-box-shadow:0 0 10px rgba(0, 204, 204, .5);  
  	-moz-box-shadow:0 0 10px rgba(0, 204, 204, .5);  
  	box-shadow:0 0 10px rgba(0, 204, 204, .5);  
}
.prebtn{
	width:138px;
	height:36px;
	
	left: 5%;
	top: 10%;
}
.backbtn{
<<<<<<< HEAD
	width:138px;
	height:36px;
	left: 58%;
=======
	left: 52%;
>>>>>>> 864c52ad507faa7dcfc345c150a3b87465f0cad7
	top: 10%;
}
.common{
	position: fixed;
	width: 60%;
	z-index: 100;	
	transition:all .4s;
	img{
		width: 80%;
		background-color: #fff;
	}
	// &.fade-enter-active{
		
	// 	transition: all 1s ease;
<<<<<<< HEAD
	// 	transform: translateX(200%);
=======
	// 	transform: translateX(-200%);
>>>>>>> 864c52ad507faa7dcfc345c150a3b87465f0cad7
	// }
	// &.fade-leave-active{
		
	// 	transition: all 1s ease;
<<<<<<< HEAD
	// 	transform: translateX(-200%);
	// }
	&.fade-enter{
  	   opacity:0;
  	   transform: translateX(0);
	}
	&.fade-leave-to{
		opacity:0;
		transform: translateX(0);
	}
	
=======
	// 	transform: translateX(200%);
	// }
	&.fade-enter{
  	   opacity:0;
  	   // transform: translateX(100%);
	}
	&.fade-leave-to{
		opacity:0;
	}
	// &.fade-leave{
	// 	transform: translateX(0);
	// }
>>>>>>> 864c52ad507faa7dcfc345c150a3b87465f0cad7
}
</style>
<script>
	export default{
		data(){
			return{
				preViewShowIndex:0,
				move:null,
			}
		},
		props:{
			preView:{
				required: true,
				default: {}
			},
			showPreview:{
				required: true,
				default: {}
			}
		},
		mounted:function(){

		},
		methods:{
			preClick:function(){
<<<<<<< HEAD
				let that = this;
				
				 that.move = "{transition: all 1s ease;transform: translateX(-200%);}";
			   
=======
				this.move="{transition: all 1s ease,transform: translateX(200%)}";
>>>>>>> 864c52ad507faa7dcfc345c150a3b87465f0cad7
				if(this.preViewShowIndex>0){
					this.preViewShowIndex--;
				}
			
				
			},
			backClick:function(){
<<<<<<< HEAD
				let that = this;
			    that.move = "{transition: all 1s ease;transform: translateX(200%);}";
			   
=======
				this.move="{transition: all 1s ease,transform: translateX(-200%)}";
>>>>>>> 864c52ad507faa7dcfc345c150a3b87465f0cad7
				if(this.preViewShowIndex<this.preView.length-1){
					this.preViewShowIndex++;
				}
				
				
				
			},
			preViewClose:function(){
				this.move=null;
				this.$emit("preViewClose");
			},
			sendJson:function(){
				let u_name = document.getElementById("uName").value;
				let u_phone = document.getElementById("uPhone").value;
				let u_adress = document.getElementById("uAdress").value;
				this.$emit("sendJson",{uName:u_name,uPhone:u_phone,uAdress:u_adress});
			}
		}

	}
</script>