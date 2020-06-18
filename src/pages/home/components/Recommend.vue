<template>
    <div>
        <div class="recommend-title">热销推荐</div>
        <ul>
            <li
                class="item border-bottom"
                v-for="item in recommendList"
                :key="item.id"
            >
                <img class="item-img" :src="item.imgUrl" />
                <div class="item-info">
                    <p class="item-title">{{ item.title }}</p>
                    <p class="item-desc">
                        {{ item.desc }}
                    </p>
                    <button class="item-button">查看详情</button>
                </div>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'HomeRecommend',
    data () {
        return {
            recommendList: [
                {
                    id: '0001',
                    imgUrl:
                        '//imgs.qunarzz.com/p/p29/201302/28/3d20251a1b60350a93835fbb.jpg_256x160_e8f468b0.jpg',
                    title: '日本樱花节',
                    desc:
                        '这里是日本一年一度的樱花节，有很多漂亮的小姐姐，很有意思哦'
                },
                {
                    id: '0002',
                    imgUrl:
                        '//imgs.qunarzz.com/p/p29/201302/28/3d20251a1b60350a93835fbb.jpg_256x160_e8f468b0.jpg',
                    title: '日本樱花节',
                    desc:
                        '这里是日本一年一度的樱花节，有很多漂亮的小姐姐，很有意思哦'
                },
                {
                    id: '0003',
                    imgUrl:
                        '//imgs.qunarzz.com/p/p29/201302/28/3d20251a1b60350a93835fbb.jpg_256x160_e8f468b0.jpg',
                    title: '日本樱花节',
                    desc:
                        '这里是日本一年一度的樱花节，有很多漂亮的小姐姐，很有意思哦'
                },
                {
                    id: '0004',
                    imgUrl:
                        '//imgs.qunarzz.com/p/p29/201302/28/3d20251a1b60350a93835fbb.jpg_256x160_e8f468b0.jpg',
                    title: '日本樱花节',
                    desc:
                        '这里是日本一年一度的樱花节，有很多漂亮的小姐姐，很有意思哦'
                },
                {
                    id: '0005',
                    imgUrl:
                        '//imgs.qunarzz.com/p/p29/201302/28/3d20251a1b60350a93835fbb.jpg_256x160_e8f468b0.jpg',
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
    .item
        overflow: hidden
        display: flex
        height: 1.9rem
        .item-img
            width: 1.7rem
            height: 1.7rem
            padding: .1rem
        .item-info
            flex: 1
            padding: .1rem
            min-width: 0
            .item-title
                line-height: .54rem
                font-size: .32rem
                ellipsis()
            .item-desc
                line-height: .4rem
                color: #ccc
                ellipsis()
            .item-button
                line-height: .44rem
                margin-top: .16rem
                background: #ff9300
                padding: 0 .2rem
                border-radius: .06rem
                color: #fff
</style>
