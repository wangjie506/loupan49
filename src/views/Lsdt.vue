<template>
	<div>
		<div class="mjjm">
			首页>楼市动态
		</div>
		<div class="home">
			<div class="leee">
				<div id="le" v-for="i in arr">
					<img :src="i.d" alt="" />
					<h4>{{i.a}}</h4>
					<span class="bbbb">{{i.b}}</span>
					<p>{{i.c}}</p>
				</div>
			</div>
			<div id="ri">
				<img src="http://ccdn.goodq.top/caches/7f72634bb4b7fbd4cacee150ae5ac686/aHR0cDovLzVhNWM1YzVmNjU5NmQudDczLnFpZmVpeWUuY29tL3FmeS1jb250ZW50L3VwbG9hZHMvMjAxOC8wMS84MzY4MTYwYTk5NWQ4OTg4YWNmNmM5NjIxYWJiYzg5My0xODAweDYwMC5qcGc_p_p100_p_3D.jpg" alt="" />
			</div>
  	</div>
	</div>
  
</template>

<script>
	export default{
		data(){
			return {
				arr:[]
			}
		},
		created(){
			this.$http.get('http://localhost:8000/news').then(p=>this.arr = p.body)
		}
	}
</script>
<style>
	.leee{
		width: 48%;
		float: left;
		margin-right: 4%;
		
	}
	.home{
		width: 100%;
		padding: 0 5%;
		box-sizing: border-box;
		overflow: hidden;
	}
	#ri{
		width: 48%;
		float: left;
	}
	#le{
		width: 100%;
		float: left;
		margin-bottom: 20px;
	}
	#le>img{
		width: 20%;
		float: left;
		margin-right: 3%;
	}
	.bbbb{
		color: #3a79e8;
		font-size: 12px;
		margin-bottom: 10px;
	}
	#le>h4{
		font-size: 16px;
		margin: 10px 0;
	}
	#le>p{
		font-size: 13px;
		color: #999;
	}
	#le h4,#le>p{
		float: left;
		width: 77%;
		word-wrap:break-word; 
		word-break:break-all;
	}
	.mjjm{
		width: 100%;
		line-height: 63px;
		font-size: 14px;
		padding: 0 80px ;
		box-sizing: border-box;
		background: #f4f4f4;
		margin-bottom: 50px;
	}
</style>