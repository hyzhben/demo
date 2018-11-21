<template>
  <div id="app">

    <div>
      <h1>01、Layout布局</h1>
      <h2>基础布局</h2>
      <p>通过基础的 24 分栏，迅速简便地创建布局。</p>
      <el-row>
        <el-col :span="24"><div> class="bg-green">没有内容就不显示</div></el-col>
      </el-row>
      <el-row>
        <el-col :span="8"><div class="bg-red">every</div></el-col>
        <el-col :span="8"><div class="bg-green">body</div></el-col>
        <el-col :span="8"><div class="bg-gray">?</div></el-col>
      </el-row>
    </div>


    <div>
      <h2>分栏间隔</h2>
      <p>Row 组件 提供 gutter 属性来指定每一栏之间的间隔，默认间隔为 0。</p>
      <el-row :gutter="20">
        <el-col :span="8"><div class="bg-red">every</div></el-col>
        <el-col :span="8"><div class="bg-green">body</div></el-col>
        <el-col :span="8"><div class="bg-gray">?</div></el-col>
      </el-row>
    </div>


    <div>
      <h2>混合布局</h2>
      <p>通过基础的 1/24 分栏任意扩展组合形成较为复杂的混合布局。</p>
      <el-row :gutter="20">
        <el-col :span="2"><div class="bg-red">every</div></el-col>
        <el-col :span="5"><div class="bg-gray">every</div></el-col>
        <el-col :span="8"><div class="bg-green">every</div></el-col>
        <el-col :span="9"><div class="bg-red">every</div></el-col>
      </el-row>
    </div>


    <div>
      <h2>分栏偏移</h2>
      <p>通过制定 col 组件的 offset 属性可以指定分栏偏移的栏数。</p>
      <el-row :gutter="20">
        <el-col :span="6"><div class="bg-green">33</div></el-col>
        <el-col :span="6" :offset="6" class="bg-red">66</el-col>
      </el-row>
    </div>


    <div>
      <h2>对齐方式</h2>
      <p>通过 flex 布局来对分栏进行灵活的对齐。</p>
      <P>将 type 属性赋值为 'flex'，可以启用 flex 布局，并可通过 justify 属性来指定 start, center, end, space-between, space-around 其中的值来定义子元素的排版方式。</p>
      <el-row type="flex" justify="start">
        <el-col :span="6"><div class="bg-red">44</div></el-col>
        <el-col :span="6"><div class="bg-green">44</div></el-col>
        <el-col :span="6"><div class="bg-gray">44</div></el-col>
      </el-row>
      <el-row type="flex" justify="center">
        <el-col :span="6"><div class="bg-red">44</div></el-col>
        <el-col :span="6"><div class="bg-green">44</div></el-col>
        <el-col :span="6"><div class="bg-gray">44</div></el-col>
      </el-row>
      <el-row type="flex" justify="end">
        <el-col :span="6"><div class="bg-red">44</div></el-col>
        <el-col :span="6"><div class="bg-green">44</div></el-col>
        <el-col :span="6"><div class="bg-gray">44</div></el-col>
      </el-row>
      <el-row type="flex" justify="space-between">
        <el-col :span="6"><div class="bg-red">44</div></el-col>
        <el-col :span="6"><div class="bg-green">44</div></el-col>
        <el-col :span="6"><div class="bg-gray">44</div></el-col>
      </el-row>
      <el-row type="flex" justify="space-around">
        <el-col :span="6"><div class="bg-red">44</div></el-col>
        <el-col :span="6"><div class="bg-green">44</div></el-col>
        <el-col :span="6"><div class="bg-gray">44</div></el-col>
      </el-row>
    </div>


    <div>
      <h2>响应式布局</h2>
      <p>参照了 Bootstrap 的 响应式设计，预设了五个响应尺寸：xs、sm、md、lg 和 xl。</p>
      <el-row :gutter="10">
        <el-col :xs="1" :sm="6" :md="12" :lg="16" :xl="24"><div class="bg-red">67</div></el-col>
        <el-col :xs="6" :sm="21" :md="15" :lg="3" :xl="10"><div class="bg-green">67</div></el-col>
      </el-row>
    </div>


    <div>
      <h2>基于断点的隐藏类</h2>
      <p></p>
    </div>

    <div>
      <h1>02、Container 布局容器</h1>
      <pre>
          用于布局的容器组件，方便快速搭建页面的基本结构：

          el-container：外层容器。当子元素中包含 el-header 或 el-footer 时，全部子元素会垂直上下排列，否则会水平左右排列。

          el-header：顶栏容器。

          el-aside：侧边栏容器。

          el-main：主要区域容器。

          el-footer：底栏容器。

以上组件采用了 flex 布局，使用前请确定目标浏览器是否兼容。此外，el-container 的子元素只能是后四者，后四者的父元素也只能是 el-container。
      </pre>

      <el-container>
        <el-header>head</el-header>
        <el-main>main</el-main>
      </el-container>
      </br>
      <el-container>
        <el-header></el-header>
        <el-main></el-main>
        <el-footer></el-footer>
      </el-container>
      </br></br>
      <el-container>
        <el-header>header</el-header>
        <el-container>
          <el-aside>aside</el-aside>
          <el-main>main</el-main>
        </el-container>
      </el-container>
    </div></br>


    <!--实例-->
    <div>
    <el-container style="height: 500px; border: 1px solid #eee">
      <el-aside width="200px" style="background-color: rgb(238, 241, 246)">
        <el-menu :default-openeds="['1', '3']">
          <el-submenu index="1">
            <template slot="title"><i class="el-icon-message"></i>导航一</template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="1-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
              <template slot="title">选项4</template>
              <el-menu-item index="1-4-1">选项4-1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-submenu index="2">
            <template slot="title"><i class="el-icon-menu"></i>导航二</template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="2-1">选项1</el-menu-item>
              <el-menu-item index="2-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="2-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="2-4">
              <template slot="title">选项4</template>
              <el-menu-item index="2-4-1">选项4-1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-submenu index="3">
            <template slot="title"><i class="el-icon-setting"></i>导航三</template>
            <el-menu-item-group>
              <template slot="title">分组一</template>
              <el-menu-item index="3-1">选项1</el-menu-item>
              <el-menu-item index="3-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="3-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="3-4">
              <template slot="title">选项4</template>
              <el-menu-item index="3-4-1">选项4-1</el-menu-item>
            </el-submenu>
          </el-submenu>
        </el-menu>
      </el-aside>

      <el-container>
        <el-header style="text-align: right; font-size: 12px">
          <el-dropdown>
            <i class="el-icon-setting" style="margin-right: 15px"></i>
            <el-dropdown-menu slot="dropdown">
              <el-dropdown-item>查看</el-dropdown-item>
              <el-dropdown-item>新增</el-dropdown-item>
              <el-dropdown-item>删除</el-dropdown-item>
            </el-dropdown-menu>
          </el-dropdown>
          <span>王小虎</span>
        </el-header>

        <el-main>
          <el-table :data="tableData">
            <el-table-column prop="date" label="日期" width="140">
            </el-table-column>
            <el-table-column prop="name" label="姓名" width="120">
            </el-table-column>
            <el-table-column prop="address" label="地址">
            </el-table-column>
          </el-table>
        </el-main>
      </el-container>
    </el-container>

    </div>
  </br></br>




    <div>
      <h1>03、Color 色彩</h1>
      <el-container>
        <el-row type="flex" justify="space-around">
          <el-col :span="6"><div class="bg-blue">主色Element 主要品牌颜色是鲜艳、友好的蓝色。Blue</div></el-col>
          <el-col :span="6"><div class="bg-Success">辅助色Success</div></el-col>
          <el-col :span="6"><div class="bg-Warning">Warning</div></el-col>
          <el-col :span="6"><div class="bg-Danger">Danger</div></el-col>
          <el-col :span="6"><div class="bg-Info">辅助色Info</div></el-col>
        </el-row>
      </el-container>
      <pre>中性色
        中性色用于文本、背景和边框颜色。通过运用不同的中性色，来表现层次结构。

        主要文字 #303133
        常规文字 #606266
        次要文字 #909399
        占位文字 #C0C4CC
        一级边框 #DCDFE6
        二级边框 #E4E7ED
        三级边框 #EBEEF5
        四级边框 #F2F6FC
      </pre>
    </div>
    </br></br>


    <div>
      <h1>04、Typography 字体</h1>
    </div>

    <div>
      <h1>05、Icon 图标</h1>
      <el-row :gutter="20" type="flex" justify="space-around">
        <el-col :span="3"><i class="el-icon-edit"></i></el-col>
        <el-col :span="3"><i class="el-icon-share"></i></el-col>
        <el-col :span="3"><i class="el-icon-delete"></i></el-col>
        <el-col :span="3"><i class="el-icon-loading"></i></el-col>
        <el-col :span="3"><el-button type="primary" icon="el-icon-search">搜索</el-button></el-col>
      </el-row>
    </div>


    <div>
      <h1>06、Button 按钮</h1>
      使用type、plain、round和circle属性来定义 Button 的样式。
      <el-row>
        <el-button>默认按钮</el-button>
        <el-button type="primary">主要按钮primary</el-button>
        <el-button type="success">成功按钮success</el-button>
        <el-button type="info">信息按钮info</el-button>
        <el-button type="warning">警告按钮warning</el-button>
        <el-button type="danger">危险按钮danger</el-button>
      </el-row>

      <el-row>
        <el-button plain>朴素按钮plain</el-button>
        <el-button type="primary" plain>主要按钮</el-button>
        <el-button type="success" plain>成功按钮</el-button>
        <el-button type="info" plain>信息按钮</el-button>
        <el-button type="warning" plain>警告按钮</el-button>
        <el-button type="danger" plain>危险按钮</el-button>
      </el-row>

      <el-row>
        <el-button round>圆角按钮round</el-button>
        <el-button type="primary" round>主要按钮</el-button>
        <el-button type="success" round>成功按钮</el-button>
        <el-button type="info" round>信息按钮</el-button>
        <el-button type="warning" round>警告按钮</el-button>
        <el-button type="danger" round>危险按钮</el-button>
      </el-row>

      <el-row>
        <el-button icon="el-icon-search" circle>circle</el-button>
        <el-button type="primary" icon="el-icon-edit" circle></el-button>
        <el-button type="success" icon="el-icon-check" circle></el-button>
        <el-button type="info" icon="el-icon-message" circle></el-button>
        <el-button type="warning" icon="el-icon-star-off" circle></el-button>
        <el-button type="danger" icon="el-icon-delete" circle></el-button>
      </el-row>

      <el-row>
        <el-button type="primary" icon="el-icon-check">主要按钮</el-button>
        <el-button type="danger" icon="el-icon-delete" disabled>删除按钮</el-button>
        <el-button type="info">信息按钮</el-button>
        <el-button type="success">危险按钮</el-button>
      </el-row>

      <el-row>
        <el-button type="text">文字按钮</el-button>
        <el-button type="text" disabled>文字按钮</el-button>
      </el-row>

      <el-button-group>
        <el-button type="primary" icon="el-icon-delete">登录</el-button>
        <el-button type="danger" icon="el-icon-delete">重置</el-button>
        <el-button type="success" icon="el-icon-delete">注册</el-button>
      </el-button-group>

      <el-button type="primary" :loading="true">加载中</el-button>
    </div>




    <div>
      <h1>Radio 单选框</h1>
      <p>
        由于选项默认可见，不宜过多，若选项过多，建议使用 Select 选择器。
        要使用 Radio 组件，只需要设置v-model绑定变量，选中意味着变量的值为相应 Radio label属性的值，label可以是String、Number或Boolean。
      </p>
      <el-radio v-model="radio" label="选项1">LOL</el-radio>
      <el-radio v-model="radio" label="选项2">炉石</el-radio>
      <el-radio disabled v-model="radio" label="选项3">学习</el-radio>
      <el-radio v-model="radio" label="选项4">飞车</el-radio>

      <el-radio-group v-model="radio2">
        <el-radio :label="1">单选框组</el-radio>
        <el-radio :label="2">单选框组</el-radio>
        <el-radio :label="3">单选框组</el-radio>
      </el-radio-group>
      <br><br>
      <el-radio-group v-model="radio2" size="mini">
        <el-radio-button :label="1">按钮样式</el-radio-button>
        <el-radio-button :label="2">el-radio-button</el-radio-button>
        <el-radio-button :label="3">单选框组</el-radio-button>
      </el-radio-group>
      <br><br>
      <el-radio-group v-model="radio2" disabled>
        <el-radio-button :label="1">disabled</el-radio-button>
        <el-radio-button :label="2">单选框组</el-radio-button>
        <el-radio-button :label="3">单选框组</el-radio-button>
      </el-radio-group>
      <br><br>
      <el-radio-group v-model="radio2">
        <el-radio :label="1" >border</el-radio>
        <el-radio :label="2" border>带边框</el-radio>
        <el-radio :label="3" border>单选框组</el-radio>
      </el-radio-group>
      <br><br>
    </div>

		
		

    <div>
 			<h1>Checkbox 多选框</h1>
 			<h3>基础用法</h3>
        <p>在el-checkbox元素中定义v-model绑定变量，单一的checkbox中，默认绑定变量的值会是Boolean，选中为true。</p>
        <el-checkbox v-model="checked">checkbox</el-checkbox>
      
      <h3>禁用状态</h3>
        <el-checkbox disabled>禁用状态</el-checkbox>
        <el-checkbox disabled>disabled</el-checkbox>

      <h3>多选框组</h3>
        <el-checkbox-group v-model="checklist">
          <el-checkbox label="多选框组">多选框组</el-checkbox>
          <el-checkbox label="check-box-group">check-box-group</el-checkbox>
          <el-checkbox label="disabled" disabled>不可选</el-checkbox>
        </el-checkbox-group>
        
      <h3>indeterminate 状态</h3>  
      <p>indeterminate 属性用以表示 checkbox 的不确定状态，一般用于实现全选的效果</p>
        <el-checkbox :indeterminate="isIndeterminate" v-model="checkAll" @change="handleCheckAllChange">全选</el-checkbox>            
        <el-checkbox-group v-model="checkedCities" @change="handleCheckedCitiesChange">
          <el-checkbox v-for="city in cities" :label="city" :key="city">{{city}}</el-checkbox>
        </el-checkbox-group>

      <h3>可选项目数量的限制</h3>
        <p>使用 min 和 max 属性能够限制可以被勾选的项目的数量。</p>
        <el-checkbox-group v-model="checklist" :min="1" :max="4" >
          <el-checkbox label="多选框组">多选框组</el-checkbox>
          <el-checkbox label="check-box-group">check-box-group</el-checkbox>
          <el-checkbox label="dd">1</el-checkbox>
          <el-checkbox label="aa">2</el-checkbox>
          <el-checkbox label="cc">3</el-checkbox>
        </el-checkbox-group>

      <h3>按钮样式</h3>
        <p>只需要把el-checkbox元素替换为el-checkbox-button元素即可。此外，Element 还提供了size属性。</p>

      <h3>带有边框</h3>
        <p>设置border属性可以渲染为带有边框的多选框。</p>

    </div>
    
    
    <div></div>
    

    



  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
const cityOptions = ['上海', '北京', '广州', '深圳'];
export default {
 data() {
      const item = {
        date: '2016-05-02',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      };
      return {
        radio: '1',
        radio2: 2,
        checked: true,
        tableData: Array(20).fill(item),
        checklist:['disabled','多选框组'],
        checkAll: false,
        checkedCities: ['上海', '北京'],
        cities: cityOptions,
        isIndeterminate: true
      }
    },
  name: 'app',

  components: {
    HelloWorld
  },
  methods: {
      handleCheckAllChange(val) {
        this.checkedCities = val ? cityOptions : [];
        this.isIndeterminate = false;
      },
      handleCheckedCitiesChange(value) {
        let checkedCount = value.length;
        this.checkAll = checkedCount === this.cities.length;
        this.isIndeterminate = checkedCount > 0 && checkedCount < this.cities.length;
      }
    }

}

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}

.bg-red{
  background: red;
}
.bg-green{
  background: #b28b4c;
}
.bg-gray{
  background: paleturquoise;
}
  .el-main {
    background-color: #00ffcc;
    text-align: center;
    line-height: 160px;
  }
    .el-header, .el-footer {
    background-color: #B3C0D1;

  }
  .el-aside{
  background-color: #7CFC00;
  }
.bg-blue{
  background: #409EFF;
}
.bg-Success{
background: #FF0000;
}
.bg-Warning{
background: #DFF;
}
.bg-Danger{
background: #F56C6C;
}
.bg-Info{
background: #909399;
}
</style>
