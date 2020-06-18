<template>
    <div class="wrapper">
        <swiper touch-action: none :options="swiperOptions">
            <swiper-slide v-for="item of swiperList" :key="item.id">
                <img class="swiper-img" alt="" :src="item.imgUrl" />
            </swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>
<script>
export default {
    name: 'HomeSwiper',
    data () {
        return {
            swiperOptions: {
                pagination: '.swiper-pagination',
                loop: 'true',
                autoplay: 3000,
                paginationClickable: true
            },
            swiperList: [
                {
                    id: '001',
                    imgUrl:
                        '//imgs.qunarzz.com/vc/44/e9/86/95bc36c9e1c06ebd68bdfe222e.jpg_92.jpg'
                },
                {
                    id: '002',
                    imgUrl:
                        '//imgs.qunarzz.com/vc/6d/9f/35/b8ad5468f73fd60ec0ced086f6.jpg_92.jpg'
                },
                {
                    id: '003',
                    imgUrl:
                        '//imgs.qunarzz.com/vc/e3/a1/71/f498dfd3bed948d623c9093252.jpg_92.jpg'
                }
            ]
        }
    }
}
</script>

<style lang="stylus" scoped>
.wrapper >>> .swiper-pagination-bullet-active
    background: #fff
.wrapper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 30.43%
    background: #eee
.swiper-img
    width: 100%
</style>
