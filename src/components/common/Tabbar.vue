<template>
	<div class="Tabbar">		
		<ul>
			<li v-for="(item,index) in TabbarData" :key="index" @click="imgClick(item.path)">
				<img :src='$route.path.includes(item.path) ? item.selectedImg:item.img'></img>
				<span>{{item.text}}</span> 
			</li>
		</ul>
	</div>
</template>

<script>
export default {
	name: 'Tabbar',
	data() {
		return { 
			TabbarData: [
				{
					img: './images/home.png',
					text: '首页',
					selectedImg:'./images/home-select.png',
					path: '/home'
				},
				{
						img: './images/list.png',
						text: '分类',
						selectedImg:'./images/list-select.png',
						path: '/list'
				},
				{
					img: './images/cart.png',
					text: '购物车',
					selectedImg:'./images/cart-select.png',
					path: '/cart'
				},
				{
					img: './images/my.png',
					text: '我的',
					selectedImg:'./images/my-select.png',
				  path: '/my'
				}			
			]
		}
	},
	methods: {
		imgClick(path) { 
			this.$router.push(path);
		} 
	}
}
</script>

<style lang="less" scoped>
	.Tabbar {
		width: 100vw;
		position:fixed;
		height: 2rem;
		bottom: 0px;
		background-color: #fff;
		ul li {
			float: left;
			width: 25%;
			display: flex;
			flex-direction: column;
			align-items: center;
			justify-content: center;
			img {
				width: 1rem;
			}
			span { 
				font-size: 16px;
			}
		}
	}
</style>