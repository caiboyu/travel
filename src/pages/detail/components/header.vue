<template>
   <div>
	   <router-link tag="div" to="/" class="header-abs">
	   	    <div class="iconfont header-abs-back">&#xe624;</div>
	   </router-link>
	   <div class="header-fixed">
	   	    <div class="header">
		        <router-link to="/">
		        	<div class="iconfont header-back">&#xe624;</div>
		        </router-link>
		    </div>
	   </div>
	   
   </div>
</template>

<script>
export default {
	name: "DetailHeader"
}
</script>

<style lang="stylus" scoped>
@import '~styles/varibles.styl'
    .header-abs
        position:absolute
        top:.2rem
        left:.2rem
        width:.8rem
        height:.8rem
        line-height:.8rem
        text-align:center
        border-radius:.4rem
        background:rgba(0, 0, 0, 0.8)
        .header-abs-back
            color:#fff
            font-size:.4rem
    .header-fixed
        position:fixed
        top:0
        left:0
        right:0
        height:.86rem
        line-height:.86rem
        text-align:center
        color:#fff
        background:$bgColor
        font-size:.32rem
        .header-back
            position:absolute
            top:0
            left:0
            width:.64rem
            text-align:center
            font-size:.4rem
            color:#fff
</style>