<template>
  <div class="about">
    <h1>树形控件一键展开关闭测试</h1>

        <el-tree  :data="data" :props="defaultProps" ref='tree' node-key="id"></el-tree>

        <el-button type="primary" @click="zhankai" round>主要按钮</el-button>

  </div>
</template>

<script>
export default {
  data() {
    return {
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




