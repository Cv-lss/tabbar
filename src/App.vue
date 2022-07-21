<template>
    <div>
        <MyHeader title="标题"></MyHeader>
        <div style="padding-top:45px">
            <component :is="comName"></component>
        </div>
        <MyTabBar :list="tabList"></MyTabBar>
    </div>
</template>

<script>
import MyHeader from '@/components/MyHeader.vue'
import MyTabBar from '@/components/MyTabBar.vue'
import MyGoodsList from '@/views/MyGoodList.vue'
import MyGoodsSearch from '@/views/MySearch.vue'
import MyUserInfo from '@/views/MyInfo.vue'
export default {
    data() {
        return {
            comName: 'MyGoodsList',

            tabList: [
                {
                    iconText: "icon-shangpinliebiao",
                    text: "商品列表",
                    componentName: "MyGoodsList"
                },
                {
                    iconText: "icon-sousuo",
                    text: "商品搜索",
                    componentName: "MyGoodsSearch"
                },
                {
                    iconText: "icon-user",
                    text: "我的信息",
                    componentName: "MyUserInfo"
                }
            ],

        }
    },

    components: {
        MyHeader,
        MyTabBar,
        MyGoodsList,
        MyGoodsSearch,
        MyUserInfo
    },


}
</script>

<style>
</style>