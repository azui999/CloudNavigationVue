<template>
    <div id="NavMenu">
        <el-menu
                :default-active="activeIndex"
                class="el-menu-demo"
                mode="horizontal"
                @select="handleSelect"
                router
        >
            <template v-for="item in navMenuData">
                <el-menu-item :index="item.index" v-if="!item.child">{{item.name}}</el-menu-item>

                <el-submenu :index="item.index" v-if="item.child">
                    <template slot="title">{{item.name}}</template>
                    <template v-for="item2 in item.child">
                        <el-menu-item :index="item2.index">{{item2.name}}</el-menu-item>
                    </template>
                </el-submenu>
            </template>
        </el-menu>
    </div>
</template>

<script>
    export default {
        name: "NavMenu",
        data() {
            return {
                activeIndex: "/",
                navMenuData: [
                    { index: "/", name: "主页" },
                    { index: "/test", name: "测试" },
                    {
                        index: "2",
                        name: "我的工作台",
                        child: [{ index: "2-1", name: "选项1" },{ index: "2-2", name: "选项2" },{ index: "2-3", name: "选项3" }]
                    },

                ]
            };
        },
        methods: {
            handleSelect(key, keyPath) {
                console.log(key, keyPath);
            }
        },
        mounted(){
            this.activeIndex = this.$route.path
        }
    };
</script>

<style scoped>
</style>