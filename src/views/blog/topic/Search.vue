<template>
    <!--姚之琳-->
    <div>
        <div class="searchBar">
            <mu-button icon slot="left" id="return">
                <mu-button flat to="/blog/topic/recommend" >返回</mu-button>
                <!--<mu-icon value="close" flat to="/blog/topic/recommend"></mu-icon>-->
            </mu-button>
            <mu-auto-complete v-model="val"></mu-auto-complete>
            <mu-button icon slot="right" @click="add" id="searchicon">
                <mu-icon value="search"></mu-icon>
            </mu-button>
            <mu-divider></mu-divider>
        </div>
        <div class="topSearch">
            <mu-list>
                <span  class="subtitle">大家都在搜</span>
                <!--<mu-sub-header class="subtitle">大家都在搜</mu-sub-header>-->
                <ul >
                    <li v-for="(val,index) in hotList" class="excel">
                        {{index + 1}} {{val.content}}
                    </li>
                </ul>
            </mu-list>
        </div>
        <mu-divider></mu-divider>
        <div class="searchHistory">
            <mu-list>
                <div id="historyHeight">
                    <span id="history" class="subtitle">搜索历史</span>
                    <mu-button icon slot="right" id="icon"@click="deleteAll()" >
                        <mu-icon value="delete" ></mu-icon>
                    </mu-button>
                </div>

                <ul >
                    <li v-for="(content,index) in arr" class="historyList">
                        {{content.value}}
                        <mu-button icon slot="right" @click="del(index)" class="closeButton">
                            <mu-icon value="close" size=12></mu-icon>
                        </mu-button>
                    </li>
                </ul>
            </mu-list>
        </div>

    </div>
</template>

<script>

    export default {
        name: "Search",
        data () {
            return {
                val: '',
                arr:[],
                hotList:[
                    {
                        content:'拖拉机大减价',

                    },
                    {
                        content:'玉米种子大甩卖',

                    },
                    {
                        content:'挖掘机技术哪家强',

                    },
                    {
                        content:'水稻一年种三季的秘密',

                    },
                ]
            }
        },
        methods:{
            add(){
                if(this.val != ''){
                    this.arr.push({value:this.val});
                    this.val = '';
                }

            },
            del(index){
                this.arr.splice(index,1);
            },
            deleteAll(){
                this.arr = []
            },
        }
    }
</script>


<style scoped>
    *{
        margin: 0;
        padding: 0;
    }
    #icon {
        float: right;
        height: 50px;
        width: 50px;
    }
    #history {
        float: left;
    }
    #historyHeight{
        height: 50px;
    }
    .excel {
        width:50%;
        float:left;
    }
    .closeButton {
        float:right;
    }
    li ,.subtitle{
        list-style: none;
        padding-left: 20px;
        height: 50px;
        line-height: 50px;
    }
    .searchBar{
        text-align: center;

    }
    #searchicon{
        float:right
    }

</style>
