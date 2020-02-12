<template>
    <div>
       <el-radio-group v-model="radio">
            <el-radio @change="dayin" :label="3" disabled>备选项</el-radio>
            <el-radio @change="dayin" :label="6" >备选项</el-radio>
            <!-- <el-radio @change="dayin" :label="9" :disabled="this.radio != 9 ? disabled : false">备选项</el-radio> -->
        </el-radio-group> 
        <hr>
        <el-tooltip content="Top center" placement="top" :hideAfter="hideafter" :v-model="a">
            <el-button @click="show($event)" >Dark</el-button>
        </el-tooltip>

        <div class="mask" v-show="mask">
            <div class="f" @click="show1">
                返回
            </div>
        </div>
        1111111
    </div>
</template>

<script>
export default {
    data() {
        return {
            a:true,
            radio: 6,
            disabled:false,
            mask:false,
            enterable:true,
            hideafter:0,
        }
    },
    methods: {
        dayin(){
            console.log(this.radio)
        },
        show(e){
            console.log(e)
            this.mask = !this.mask
            this.hideafter = 4000
            // this.disabled = !this.disabled
            // this.enterable = !this.enterable
        },
        show1(){
            this.mask = !this.mask
            this.hideafter = 0
            // this.disabled = !this.disabled
            // this.enterable = !this.enterable
        }
    },
}
</script>

<style lang="less" scoped>
    .mask {
        position: fixed;
        top: 0;
        left: 0;
        right: 0;
        bottom: 0;
        background: rgba(0, 0, 0, 0.3);
        z-index: 10;
            .f{
                width:562px;
                height:280px;
                background:rgba(255,255,255,1);
                border-radius:12px;
                position: absolute;
                top: 35%;
                // top: calc(50% - 140px);
                left: calc(50% - 281px);
                padding: 23px 0 28px 31px;
            }
    }
</style>