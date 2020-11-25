<template>
    <div class="account-wrap">
        <head-title :title="'记账：'"></head-title>
        <Tabs>
            <TabPane label="消费">
                <dl style="text-align: center;line-height: 40px;font-size: 16px;">
                    <dt style="font-weight: bold; font-size: 18px">消费类型:</dt>
                    <dd @click="toDetail('consumption', '水果零食')" style="cursor: pointer">水果零食</dd>
                    <dd @click="toDetail('consumption', '餐饮伙食')" style="cursor: pointer">餐饮伙食</dd>
                    <dd @click="toDetail('consumption', '出行旅游')" style="cursor: pointer">出行旅游</dd>
                    <dd @click="toDetail('consumption', '网上购物')" style="cursor: pointer">网上购物</dd>
                    <dd @click="toDetail('consumption', '生活日常')" style="cursor: pointer">生活日常</dd>
                    <dd @click="toDetail('consumption', '租房水电')" style="cursor: pointer">租房水电</dd>
                    <dd @click="toDetail('consumption', '医疗药物')" style="cursor: pointer">医疗药物</dd>
                    <dd @click="toDetail('consumption', '其它消费')" style="cursor: pointer">其它消费</dd>
                </dl>
            </TabPane>
            <TabPane label="入账">
                <dl style="text-align: center;line-height: 40px;font-size: 16px;">
                    <dt style="font-weight: bold; font-size: 18px">消费类型:</dt>
                    <dd @click="toDetail('earn', '水果零食')" style="cursor: pointer">水果零食</dd>
                    <dd @click="toDetail('earn', '餐饮伙食')" style="cursor: pointer">餐饮伙食</dd>
                    <dd @click="toDetail('earn', '出行旅游')" style="cursor: pointer">出行旅游</dd>
                    <dd @click="toDetail('earn', '网上购物')" style="cursor: pointer">网上购物</dd>
                    <dd @click="toDetail('earn', '生活日常')" style="cursor: pointer">生活日常</dd>
                    <dd @click="toDetail('earn', '租房水电')" style="cursor: pointer">租房水电</dd>
                    <dd @click="toDetail('earn', '医疗药物')" style="cursor: pointer">医疗药物</dd>
                    <dd @click="toDetail('earn', '其它消费')" style="cursor: pointer">其它消费</dd>
                </dl>
            </TabPane>
        </Tabs>
    </div>
</template>
<script>
    import types from '../../../store/mutation-types'
    import headTitle from '../../../components/head-title.vue'
    export default {
        name: 'account_index',
        created () {
            this.setNavIndex();
        },
        components: {
            headTitle
        },
        methods: {
            toDetail (name, val) {
              this.$router.push({
                  name,
                  query: {
                      account_type: val
                  }
              })
            },
            setNavIndex () {
                this.$store.commit(types.SET_NAV_INDEX,'2')
            }
        }
    }
</script>
<style lang="scss">
    @import "../../../assets/scss/define";
    .ivu-tabs-nav {
        width: 100%;
        display: flex;
        justify-content: space-around;
    }
    .go-btn-box{
        @extend %pa;
        @extend %tac;
        @extend %f14;
        @extend %cfff;
        @extend %l0;
        @extend %r0;
        @extend %t50;
        transform: translate3d(0,-50%,0);
    }
    .go-account{
        @extend %db;
        @extend %cp;
        @extend %cfff;
        margin: 0 auto 20px;
        width: 150px;
        height: 35px;
        line-height: 35px;
        border-radius: 5px;
        &.go-consumption{
            background-color: #FF4949;
            box-shadow: 0 3px 0 0 red;
        }
        &.go-earn{
            background-color: #69ce72;
            box-shadow: 0 3px 0 0 #13CE66;
        }
    }
</style>

