<template>
    <div>
        <div class="banner" @click="handleBannerClick">
            <img
                class="banner-img"
                src="https://timgsa.baidu.com/timg?image&quality=80&size=b9999_10000&sec=1592909151948&di=3e52fbcb1c43042d06eb1f7430daa530&imgtype=0&src=http%3A%2F%2Ft9.baidu.com%2Fit%2Fu%3D1307125826%2C3433407105%26fm%3D79%26app%3D86%26f%3DJPEG%3Fw%3D5760%26h%3D3240"
            />
            <div class="banner-info">
                <div class="banner-title">这是美女啊</div>
                <div class="banner-number">
                    <span class="iconfont banner-icon">&#xe64a;</span>
                    39
                </div>
            </div>
        </div>
        <common-gallary :imgs="imgs" v-show="showGallary" @close="handleGallaryClose"></common-gallary>
    </div>
</template>

<script>
import axios from 'axios'
import CommonGallary from 'common/gallary/Gallary'
export default {
    name: 'DetailBanner',
    components: {
        CommonGallary
    },
    data () {
        return {
            imgs: [],
            showGallary: false
        }
    },
    methods: {
        getDetailInfo () {
            axios.get('/api/detail.json').then(this.getDetailSucc)
        },
        getDetailSucc (res) {
            res = res.data
            if (res.ret && res.data) {
                const data = res.data
                this.imgs = data.gallaryImgs
            }
        },
        handleBannerClick () {
            this.showGallary = true
        },
        handleGallaryClose (msg) {
            this.showGallary = false
        }
    },
    mounted () {
        this.getDetailInfo()
    }
}
</script>

<style lang="stylus" scoped>
.banner
    position: relative
    overflow: hidden
    height: 0
    padding-bottom: 55%
    .banner-img
        width: 100%
    .banner-info
        position: absolute
        display: flex
        left: 0
        right: 0
        bottom: 0
        line-height: .6rem
        color: #fff
        background-image: linear-gradient(top, rgba(0, 0, 0, 0), rgba(0, 0, 0, 0.8))
        .banner-title
            flex: 1
            font-size: .32rem
            padding: 0 .2rem
        .banner-number
            padding: .05rem .4rem 0
            margin-top: .14rem
            height: .32rem
            line-height: .32rem
            border-radius: .2rem
            background: rgba(0, 0, 0, .8)
            font-size: .24rem
            .banner-icon
                font-size: .24rem
</style>
