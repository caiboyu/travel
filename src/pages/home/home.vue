<template>
	<div>
		<home-header></home-header>
		<home-swiper :list="swiperList"></home-swiper>
		<home-icons :list="iconList"></home-icons>
		<home-recommend :list="recommendList"></home-recommend>
		<home-weekend :list="weekendList"></home-weekend>
	</div>
</template>

<script>
import HomeHeader from './components/header'
import HomeSwiper from './components/swiper'
import HomeIcons from './components/icons'
import HomeRecommend from './components/recommend'
import HomeWeekend from './components/weekend'
import axios from 'axios'
import { mapState } from 'vuex'
export default {
	name: "Home",
//	注册声明局部组件
    components: {
    	HomeHeader,
    	HomeSwiper,
    	HomeIcons,
    	HomeRecommend,
    	HomeWeekend
    },
    data () {
    	return {
    		swiperList: [],
    		iconList: [],
    		recommendList: [],
    		weekendList: [],
    		lastCity: ''
    	}
    },
    methods: {
    	getHomeInfo () {
    		axios.get("https://easy-mock.com/mock/5bd2c1e6109df2491b1f9c62/travel/index?city=" +this.city )
    	      .then(this.getHomeInfoSucc)
    	},
    	getHomeInfoSucc (res) {
    		res = res.data
    		if (res.ret && res.data) {
    			const data = res.data
    			this.swiperList = data.swiperList
    			this.iconList = data.iconList
    			this.recommendList = data.recommendList
    			this.weekendList = data.weekendList
    		}
    	}
    },
    mounted () {
    	this.lastCity = this.city
    	this.getHomeInfo()
    },
    computed: {
    	...mapState(['city'])
    },
    activated () {
    	if (this.lastCity !== this.city) {
    		this.lastCity = this.city
    	    this.getHomeInfo()
    	}
    	console.log('activated')
    }
}
</script>

<style scoped>
</style>