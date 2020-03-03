<template>
    <div>
        <div class="a">
            <el-button type="primary" @click="tishi" >点击提示</el-button>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            
        }
    },
    methods: {
        tishi(){
            this.$message({
                message: '警告哦，这是一条警告消息,警告哦，这是一条警告消息警告哦，这是一条警告消息警告哦，这是一条警告消息',
                type: 'warning',
                duration: 30000,
            });
        }
    },  
}
</script>

<style lang="less" >
    
    
</style>