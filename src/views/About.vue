<template>
  <div class="about">
    <h1>树形控件一键展开关闭测试</h1>
      
          <el-date-picker
          v-model="input1"
          type="date"
          prefix-icon="el-icon-kzcooperate"
          placeholder="选择日期">
          </el-date-picker>
      <i class="el-icon-kzcooperate"></i>


      <el-tree 
        :data="data" 
        :props="defaultProps" 
        ref='tree'
        node-key="id"
      >
      
      </el-tree>



 <el-button type="primary" @click="zhankai" round>主要按钮</el-button>


      <el-table
        :data="tableData"
      >
               <!-- <el-table-column type="selection" :reserve-selection="true"></el-table-column> -->

          <template v-for="(item,index) in tableHead">
    <el-table-column :prop="item.column_name" :label="item.column_comment" :key="index" :type="item.type11" v-if="item.column_name != 'id'"></el-table-column>
  </template>
      </el-table>




  </div>
</template>

<script>


export default {
  data() {
    return {
      tableData:[
        {
            name:'a'
        },
        {
            name:'b'
        },
        {
            name:'c'
        },
      ],

tableHead:[
    {
      column_name: "column_name",column_comment:"姓名",type11:'index',
    },
    {
      column_name: "column_age",column_comment:"年龄",type11:'expand',
    },
    {
      column_name: "column_sex",column_comment:"性别",type11:'selection'
    }
], 
      input1:'',
      isexpand:true,
      data: [{
          label: '一级 1',
          id:1,
          children: [{
            label: '二级 1-1',
            id:2,
            children: [{
              label: '三级 1-1-1',
              id:3
            }]
          }]
        }, {
          label: '一级 2',
          id:4,
          children: [{
            label: '二级 2-1',
            id:5,
            children: [{
              label: '三级 2-1-1',
              id:6
            }]
          }, {
            label: '二级 2-2',
            id:7,
            children: [{
              label: '三级 2-2-1',
              id:8
            }]
          }]
        }, {
          label: '一级 3',
          id:9,
          children: [{
            label: '二级 3-1',
            id:10,
            children: [{
              label: '三级 3-1-1',
              id:11
            }]
          }, {
            label: '二级 3-2',
            id:12,
            children: [{
              label: '三级 3-2-1',
              id:13
            }]
          }]
        }],
        defaultProps: {
          children: 'children',
          label: 'label'
        }
    }
  },
  methods:{
      
      zhankai(){
        this.$nextTick(() => {
            for(var i=0;i<this.$refs.tree.store._getAllNodes().length;i++){
                  this.$refs.tree.store._getAllNodes()[i].expanded=this.isexpand;
                }
        });
        this.isexpand = !this.isexpand
      }
      
      
 
  }
}
</script>

<style src="../icon-font/icon-font.css"></style>

<style lang="sass" scoped>

</style>
