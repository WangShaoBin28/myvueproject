<template>
    <el-container>
        <div>
            <el-button @click="show = !show">Click Me</el-button>

            <div style="display: flex; margin-top: 20px; height: 100px;">
                <transition name="el-fade-in-linear">
                    <div v-show="show" class="transition-box">.el-fade-in-linear</div>
                </transition>
                <transition name="el-fade-in">
                    <div v-show="show" class="transition-box">.el-fade-in</div>
                </transition>
            </div>
            <router-link to='/hello'>
                <button>点我到第二个页面</button>
            </router-link>
            <el-button type="primary" @click="f()">点击我跳转</el-button>
        </div>
    </el-container>
</template>

<script>
    export default {
        data: () => ({
            show: true
        })
        , methods: {
            f: function () {
                console.log(this.$store.state.count++)
                // this.$router.push({path: '/hello'})
            }
        }
    }
</script>

<style>
    .transition-box {
        margin-bottom: 10px;
        width: 200px;
        height: 100px;
        border-radius: 4px;
        background-color: #409EFF;
        text-align: center;
        color: #fff;
        padding: 40px 20px;
        box-sizing: border-box;
        margin-right: 20px;
    }
</style>

