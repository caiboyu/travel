<template>
    <ul class="list">
    	<li class="item" v-for="item of letters" :key="item" :ref="item"
    		 @click="handleLetterClick"
    		 @touchstart="handleTouchStart"
    		 @touchmove="handleTouchMove"
    		 @touchend="handleTouchEnd"
    	>
    		{{item}}
    	</li>
    </ul>
</template>

<script>
export default {
	name: 'CityAlphabet',
	props: {
		cities: Object
	},
	computed: {
		letters () {
			const letters = []
			for (let i in this.cities) {
				letters.push(i)
			}
			return letters
		}
	},
	data () {
		return {
			touchStatus: false
		}
	},
	methods: {
		handleLetterClick (e) {
			this.$emit("change", e.target.innerText)//向外触发事件
			
		},
		handleTouchStart () {
			this.touchStatus = false
			
		},
		handleTouchMove (e) {
			if(this.touchStatus) {
				const startY = this.$refs['A'][0].offsetTop
				const touchY = e.touches[0].clientY
				console.log(touchY)
			}
			
		},
		handleTouchEnd () {
			this.touchStatus = false
		}
	}
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
    .list
        display:flex
        flex-direction:column
        justify-content:center
        position:absolute
        top:1.58rem
        right:0
        bottom:0
        width:.4rem
        .item
            line-height:.4rem
            text-align:center
            color: $bgColor

</style>