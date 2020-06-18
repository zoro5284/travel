<template>
    <div>
        <div class="recommend-title">周末去哪儿</div>
        <ul>
            <li
                class="item border-bottom"
                v-for="item in recommendList"
                :key="item.id"
            >
                <div class="item-img-wrapper">
                    <img class="item-img" :src="item.imgUrl" />
                </div>
                <div class="item-info">
                    <p class="item-title">{{ item.title }}</p>
                    <p class="item-desc">
                        {{ item.desc }}
                    </p>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'HomeWeekend',
    data () {
        return {
            recommendList: [
                {
                    id: '0001',
                    imgUrl:
                        '//tr-osdcp.qunarzz.com/tr-osd-tr-manager/img/5a11974656794b4715156501be10c1b7.jpg',
                    title: '日本樱花节',
                    desc:
                        '这里是日本一年一度的樱花节，有很多漂亮的小姐姐，很有意思哦'
                },
                {
                    id: '0002',
                    imgUrl:
                        '//tr-osdcp.qunarzz.com/tr-osd-tr-manager/img/5a11974656794b4715156501be10c1b7.jpg',
                    title: '日本樱花节',
                    desc:
                        '这里是日本一年一度的樱花节，有很多漂亮的小姐姐，很有意思哦'
                }
            ]
        }
    }
}
</script>

<style lang="stylus" scoped>
@import '~styles/mixins.styl'
    .recommend-title
        margin-top: .2rem
        line-height: .8rem
        background: #eee
        text-indent: .2rem
    .item-img-wrapper
        overflow: hidden
        height: 0
        padding-bottom: 33.9%
    .item-img
        width: 100%
    .item-info
        padding: .1rem
        .item-title
            line-height: .54rem
            font-size: .32rem
            ellipsis()
        .item-desc
            line-height: .4rem
            color: #ccc
            ellipsis()
</style>
