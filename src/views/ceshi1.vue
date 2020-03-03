<template>
    <div class="mixBox">
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
        <hr>

          <el-select v-model="value1" multiple placeholder="自定义" @change = daYin($event)>
                <!-- <el-option
                v-for="item in options"
                :key="item.value"
                :label="item.label"
                :value="item.value">
                </el-option> -->
                <el-option value="" disabled style="cursor: pointer;">
                    <el-checkbox v-model="checked6" @change="total($event)">全选</el-checkbox>
                </el-option>
                <el-option value="" disabled style="cursor: pointer;">
                    <el-checkbox v-model="checked" @change = xuanze1($event)>倩</el-checkbox>
                </el-option>
                <el-option value="" disabled style="cursor: pointer;">
                    <el-checkbox v-model="checked1">倩~</el-checkbox>
                </el-option>
                <el-option value="" disabled style="cursor: pointer;">
                    <el-checkbox v-model="checked2">是</el-checkbox>
                </el-option>
                <el-option value="" disabled style="cursor: pointer;">
                    <el-checkbox v-model="checked3">个</el-checkbox>
                </el-option>
                <el-option value="" disabled style="cursor: pointer;">
                    <el-checkbox v-model="checked4">傻</el-checkbox>
                </el-option>
                <el-option value="" disabled style="cursor: pointer;">
                    <el-checkbox v-model="checked5">子</el-checkbox>
                </el-option>
            </el-select>
            <hr>
            <div class="biaohge">
                <el-table
                    :data="tableData"
                    style="width: 80%">
                    <el-table-column v-for="(item,index) in tab" :key="index"
                        :prop="item.prop"
                        :label="item.label"
                        >
                    </el-table-column>
                    <!-- <el-table-column
                        prop="name"
                        label="姓名"
                        width="180">
                    </el-table-column>
                    <el-table-column
                        prop="address"
                        label="地址">
                    </el-table-column> -->
                </el-table>
            </div>
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
            options: [{
            value: '选项1',
            label: '黄金糕'
            }, {
            value: '选项2',
            label: '双皮奶'
            }, {
            value: '选项3',
            label: '蚵仔煎'
            }, {
            value: '选项4',
            label: '龙须面'
            }, {
            value: '选项5',
            label: '北京烤鸭'
            }],
            value1: '自定义',
            checked:false,
            checked1:false,
            checked2:false,
            checked3:false,
            checked4:false,
            checked5:false,
            checked6:false,
            tableData: [{
            date: '2016-05-02',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1518 弄'
          }, {
            date: '2016-05-04',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1517 弄'
          }, {
            date: '2016-05-01',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1519 弄'
          }, {
            date: '2016-05-03',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1516 弄'
          }],
          tab:[{
                prop:"date",
                label:"日期" 
              },
              {
                prop:"name",
                label:"姓名" 
              },
              {
                prop:"address",
                label:"地址" 
              }
          ],
          ceshi:[{
              name:'茶水',
              count:0,
              children:[{
                  name:'茶水1',
                 count:0,
              },{
                  name:'茶水',
                 count:1,
              },]
          },{
              name:'果盘',
              count:0,
              children:[{
                  name:'果盘1',
                 count:0,
              },{
                  name:'果盘',
                 count:1,
              },]
          },{name:'hahahah',
              count:0}]
        }
    },
    created() {
        this.init()
    },
    methods: {
        init(){
            let skip = ['果盘','茶水']
          let newList =  this.ceshi.map(item=>{
                if(skip.includes(item.name)){
                    item.children.map(it=>{
                        if(it.count){
                            item.children[0].count = it.count
                        }
                    })
                    item = item.children[0]
                }
                return item
            })
            console.log(this.ceshi,'lalal',newList)
        },
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
        },
        daYin(e){
            console.log(e)
        },
        total(e){
            if(e){
                this.checked = true
                this.checked1 = true
                this.checked2 = true
                this.checked3 = true
                this.checked4 = true
                this.checked5 = true
            }else{
                this.checked = false
                this.checked1 = false
                this.checked2 = false
                this.checked3 = false
                this.checked4 = false
                this.checked5 = false
            }
        },
        xuanze1(e){
            if(e){
                this.tab.push(
                    {
                    prop:"one",
                    label:"倩" 
                    }
                )
                // this.tableData.forEach((item)=>{
                //     item.one = '测试'
                // })
            }else{
                this.tab.forEach((item,index) => {
                    if(item.prop == 'one'){
                        this.tab.splice(index,1)
                    }
                })
                // this.tableData.forEach((item)=>{
                //     delete item.one
                // })
            }
        }
    },
}
</script>

<style lang="less" scoped>
.mixBox{
    width: 1200px;
    margin: 0 auto;
}
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
    .biaohge{
        display: flex;
        justify-content: center;
            /deep/.el-table{
                // display: flex;
            }
    }
</style>