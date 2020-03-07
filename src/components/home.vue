<template>
    <div class="home">
        <el-card class="box-card">
            <div style="height: 36px;border-bottom: 1px solid #f0f0f0;">
                <span>我的导航</span>
            </div>
            <div style="border-bottom: 1px solid #f0f0f0;">
                <el-row>
                    <el-col :span="2"><p>我的导航</p></el-col>
                    <el-col :span="22">
                        <el-row :gutter="12">
                            <el-col :span="5" v-for="(data,index) in dataList" :key="index">
                                <el-card shadow="hover" class="in-card">
                                    <div class="url" @click="go_details(data.url)">
                                        <el-image :src="data.icon" class="img">
                                            <div slot="error" class="image-slot">
                                                <img src="./img/favicon.png" width="16" height="16">
                                            </div>
                                        </el-image>
<!--                                        <img :src="data.icon" height="16" width="16">-->
                                        <span>{{data.title}}</span>
                                    </div>
                                </el-card>
                            </el-col>
                        </el-row>
                    </el-col>
                </el-row>
            </div>
        </el-card>
    </div>
</template>

<script>
    export default {
        name: "home",
        data() {
            return {
                dataList:[
                    {url:"http://www.baidu.com", icon:"http://www.baidu.com/favicon.ico",title:'百度'},
                    {url:"http://www.lljjava.cn", icon:"http://www.lljjava.com/favicon.ico",title:'lilj'},
                ]
            };
        },
        methods: {
            go_details(url) {
                console.log(url)
                window.open(url,"_blank")
            }
        },

    }
</script>

<style scoped lang="scss">
.home{
    .el-col-5 {
        width: calc(20.83333% - 9px);
        padding: 6px;
        cursor:pointer;
        .url{
            padding: 9px;
            .img{
                width: 16px;
                height: 16px;
                top: 2px;
            }
            span{
                display: inline-block;
                color: #333;
                font-size: 14px;
            }
        }
    }
}
</style>
<style lang="scss">
    .home{
        .in-card{
            .el-card__body{
                padding: 0;
            }
        }
    }
</style>