<template>
    <div>
    	<div class="banner" @click="handleClickGallary">
			<img class="banner-img" src="//img1.qunarzz.com/sight/p0/1704/c9/c936f3fccfc6d7eda3.img.jpg_600x330_1be7ea5e.jpg"/>
			<div class="banner-info">
				<div class="banner-title">上海杜莎夫人蜡像馆</div>
				<div class="banner-number"><span class="iconfont banner-icon">&#xe791;</span>28</div>
				
			</div>
		</div>
		<common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
    </div>
</template>

<script>
import CommonGallary from "common/gallary/gallary"
export default {
	name: 'DetailBanner',
	data () {
		return {
			showGallary: false,
			imgs: [
			    "http://img1.qunarzz.com/sight/p0/1704/66/668431aeff49b77ca3.img.jpg_r_800x800_25c929be.jpg",
			    "http://img1.qunarzz.com/sight/p0/1703/22/2244eaab209bf750a3.img.jpg_r_800x800_d4d9e847.jpg",
			    "http://img1.qunarzz.com/sight/p0/1704/bb/bb5bd93bb94c1d95a3.img.jpg_r_800x800_759a83aa.jpg" 
			]
		}
	},
	methods: {
		handleClickGallary () {
			this.showGallary = true
		},
		handleGallaryClose () {
			this.showGallary = false
		}
	},
	components: {
		CommonGallary
	}
}
</script>

<style lang="stylus" scoped>
    .banner
        position:relative
        overflow:hidden
        height:0
        padding-bottom:55%
        .banner-img
            width:100%
        .banner-info
            display:flex
            position:absolute
            left:0
            right:0
            bottom:0
            line-height:.6rem
            color:#fff
            background-image:linear-gradient(top,rgba(0,0,0,0),rgba(0,0,0, 0.8))
            .banner-title
                flex:1
                font-size:.32rem
                padding:0 .2rem
            .banner-number
                padding: 0 .4rem
                height:.32rem
                line-height:.32rem
                margin-top:.14rem
                border-radius:.2rem
                background:rgba(0, 0, 0, .8)
                font-size:.24rem
                .banner-icon
                     font-size:.24rem
</style>