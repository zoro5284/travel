<template>
    <div class="swiper">
        <swiper touch-action: none :options="swiperOptions" v-if="showFirstImg">
            <swiper-slide v-for="item of list" :key="item.id">
                <img class="swiper-img" alt="" :src="item.imgUrl" />
            </swiper-slide>
            <div class="swiper-pagination" slot="pagination"></div>
        </swiper>
    </div>
</template>
<script>
export default {
    name: 'HomeSwiper',
    props: {
        list: Array
    },
    data () {
        return {
            swiperOptions: {
                pagination: '.swiper-pagination',
                loop: 'true',
                autoplay: 3000,
                paginationClickable: true
            }
        }
    },
    computed: {
        showFirstImg () {
            return this.list.length
        }
    }
}
</script>

<style lang="stylus" scoped>
.swiper >>> .swiper-pagination-bullet-active
    background: #fff
.swiper
    overflow: hidden
    width: 100%
    height: 0
    padding-bottom: 30.43%
    background: #eee
.swiper-img
    width: 100%
</style>
