<template>
    <div class="cameroon-TopicBar">
    <mu-appbar style="width: 100%; height: 50px;">
        <mu-button flat to="/blog/details" slot="left">全部关注</mu-button>
        <mu-button flat to="/blog/topic/recommend"  slot="left">话题</mu-button>
        <!--search路由跳转--修改-->
        <mu-button icon slot="right">
            <mu-icon value="search" @click="jumptoSearch"></mu-icon>
        </mu-button>
    </mu-appbar>
    <mu-appbar style="width: 100%;height: 30px;" title="">
        <mu-container class="button-wrapper">
            <mu-button flat to="/blog/topic/fellow">关注</mu-button>
            <mu-button flat to="/blog/topic/recommend">推荐</mu-button>
            <mu-button flat to="/blog/topic/hotlist">热榜</mu-button>
            <!--<mu-button flat to="/blog/topic/alists">回答</mu-button>-->
        </mu-container>
    </mu-appbar>
    </div>
</template>

<script>
    export default {
        name: "CommonHeader",
        methods:{
            //search跳转页面路由
            jumptoSearch(){
                this.$router.push('/blog/search')
            }
            //search跳转页面路由
        }
    }
</script>

<style scoped lang="scss">
    .mu-elevation-4{
        -webkit-box-shadow:none;
        box-shadow:none;
    }
    .mu-appbar{
        background-color: #ffffff;
    }
    #cameroon-topic{
        background: #eeeeee;
    }
    .button-wrapper {
        text-align: center;
        .mu-button{
            display: block;
            float: left;
            /*margin: 20px;*/
            width: 103px;
            height: 30px;
        }
        .router-link-active{
            border-bottom: solid 2px black;
        }
    }
</style>