<template>
    <div class="goods">
        <div class="menu-wrapper">
            <ul>
                <li v-for="(item,index) in goods" :key="index" class="menu-item">
                    <span class="text border-1px" >
                        {{item.name}}
                    </span>
                </li>
            </ul>
        </div>
        <div class="foods-wrapper">
            <ul>
                <li v-for='(item,index) in goods' :key="index" class="food-list">
                    <h1 class="title">{{item.name}}</h1>
                    <ul>
                        <li v-for='(food,index) in item.foods' :key="index" class="food-item border-1px">
                            <div class="icon">
                                <img :src="food.avatar" width="57" height="57">
                            </div>
                            <div class="content">
                                <h2 class="name">{{food.name}}</h2>
                                <p class="desc">{{food.description}}</p>
                                <div class="extra">
                                    <span>月售{{food.sellCount}}</span>
                                    <span>好评率{{food.rating}}%</span>
                                </div>
                                <!-- <div class="price">
                                    <span>￥{{food.price}}</span>
                                    <span v-show="food.oriPrice">￥{{food.oriPrice}}</span>
                                </div> -->
                            </div>
                        </li>
                    </ul>
                </li>
            </ul>
        </div>
    </div>
</template>
<script>
export default {
    props:{
        
    },
    data(){
        return {
            goods:[{
                type:0,
                name:'水果',
                foods:[{
                    name:"皮蛋瘦肉粥",
                    avatar:'http://static.devjackcat.com/avatar.jpeg',
                    price:10,
                    oldPrice:'',
                    description: '咸粥',
                    sellCount:229,
                    ratting:100,
                    info:'一晚皮蛋瘦肉粥一晚皮蛋瘦肉粥一晚皮蛋瘦肉粥一晚皮蛋瘦肉粥一晚皮蛋瘦肉粥',
                    ratings:[{
                        username:'1****2',
                        rateTime:1469281964000,
                        rateType:0,
                        text:'很喜欢的粥',
                        avatar:'http://static.devjackcat.com/avatar.jpeg'
                    }] 
                }]
            },{
                type:1,
                name:'下午茶'
            },{
                type:2,
                name:'甜点'
            },{
                type:3,
                name:'美食'
            },{
                type:0,
                name:'水果'
            },{
                type:1,
                name:'下午茶'
            },{
                type:2,
                name:'甜点'
            },{
                type:3,
                name:'美食'
            },{
                type:0,
                name:'水果'
            },{
                type:1,
                name:'下午茶'
            },{
                type:2,
                name:'甜点'
            },{
                type:3,
                name:'美食'
            }]
        }
    },
    created () {
		this.classMap = ['decrease', 'discount', 'guarantee', 'invoice', 'special']
	},
}
</script>
<style lang="stylus">
    @import '../../common/stylus/mixin'
    .goods
        display flex
        position absolute
        top 174px
        bottom 46px
        width 100%
        overflow hidden
        ul,li 
            padding 0
            text-align center
        .menu-wrapper
            flex 0 0 80px
            width 80px
            background #f3f5f7
            .menu-item
                display table
                height 54px
                width 100%
                line-height 14px
                .text
                    display table-cell
                    width 56px
                    vertical-align middle
                    font-size 12px
                    border-1px(rgba(7,17,27,0.1))
                list-style-type none
        .foods-wrapper
            flex 1
            .title
                padding-left 14px
                height 26px
                line-height 26px
                border-left 2px solid #d9dde1
                font-size 12px
                color rgb(147,153,159)
                background #f3f5f7
            .food-item
                display flex
                margin 18px
                padding-bottom 18px
                border-1px(rgba(7,17,27,0.1))
                &.last-child
                    border-none()
                    margin-bottom 0
                .icon
                    flex 0 0 57px
                    margin-right 10px
                .content
                    flex 1
                    text-align left 
                    .name
                        margin 2p 0 8px 0
                        height 14px
                        line-height 14px
                        font-size 14px
                        color rgb(7,17,27)
                    .desc, .extra 
                        line-height 10px
                        font-size 10px
                        // color rgb(147,153,159)/
                        color rgb(7,17,27)
                    .desc
                        margin-bottom: 8px
                        color rgb(7,17,27)
                    .extra
                        line-height 10px
                        color rgb(7,17,27)

</style>


