<template>
    <div>
        <!-- <el-tree
            :data="treeData"
            :props="defaultProps"
            ref="tree"
            >
        </el-tree> -->

        <van-uploader
          v-model="fileList"
          multiple
          :max-count="2"
          :after-read="afterRead"
          preview-image
          preview-full-image
          deletable
        />

      <div class="baba">
        <div class="tu">
            <img :src="img" alt="">
        </div>
        <div class="text">
          我快乐番薯联合会史蒂芬霍金看来是大家给大家看撒两个环节疯狂拉黑地方撒即可过隆华书店就爱看系诶啊放点那就给你的时间阿卡都是把东北三门，高度傻逼你没改的撒改变昂达的阿高大上阿高大上按规定三高度撒高度撒高度撒高度撒高度撒高度撒干撒高度撒盎司大高度撒大概傻瓜按时 华书店就爱看系诶啊放点那就给你的时间阿卡都是把东北三门，高度傻逼你没改的撒改变昂达的阿高大上阿高大上按规定三高度撒高度撒高度撒高度撒高度撒高度撒干撒高度撒盎司大高度撒大概傻瓜按时 华书店就爱看系诶啊放点那就给你的时间阿卡都是把东北三门，高度傻逼你没改的撒改变昂达的阿高大上阿高大上按规定三高度撒高度撒高度撒高度撒高度撒高度撒干撒高度撒盎司大高度撒大概傻瓜按时 华书店就爱看系诶啊放点那就给你的时间阿卡都是把东北三门，高度傻逼你没改的撒改变昂达的阿高大上阿高大上按规定三高度撒高度撒高度撒高度撒高度撒高度撒干撒高度撒盎司大高度撒大概傻瓜按时 华书店就爱看系诶啊放点那就给你的时间阿卡都是把东北三门，高度傻逼你没改的撒改变昂达的阿高大上阿高大上按规定三高度撒高度撒高度撒高度撒高度撒高度撒干撒高度撒盎司大高度撒大概傻瓜按时 华书店就爱看系诶啊放点那就给你的时间阿卡都是把东北三门，高度傻逼你没改的撒改变昂达的阿高大上阿高大上按规定三高度撒高度撒高度撒高度撒高度撒高度撒干撒高度撒盎司大高度撒大概傻瓜按时 华书店就爱看系诶啊放点那就给你的时间阿卡都是把东北三门，高度傻逼你没改的撒改变昂达的阿高大上阿高大上按规定三高度撒高度撒高度撒高度撒高度撒高度撒干撒高度撒盎司大高度撒大概傻瓜按时 华书店就爱看系诶啊放点那就给你的时间阿卡都是把东北三门，高度傻逼你没改的撒改变昂达的阿高大上阿高大上按规定三高度撒高度撒高度撒高度撒高度撒高度撒干撒高度撒盎司大高度撒大概傻瓜按时 
        </div>
        <div class="tu">
            <img :src="img1" alt="">
        </div>
      </div>




    </div>

</template>

<script>
export default {
    data() {
        return {
          img:require('@/assets/add.png'),
          img1:require('@/assets/back.png'),
           fileList: [],
            treeData:[{
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
            },
        }
    },
    methods: {
      afterRead(file) {
      // 此时可以自行将文件上传至服务器
      console.log(file);
    }
    }
}
</script>


<style lang="less" scoped>
.baba{
  width: 900px;
  min-height: 20px;
  display: flex;
  background: #eee;
  margin: 0 auto;
}
.tu{
  width: 50px;
  background: #666;
}
.text{
  flex: 1;
  text-align: start;
}
</style>