## 查看修饰符
[查看访问修饰符](https://blog.csdn.net/beiouwolf/article/details/7090700)
```
<!DOCTYPE  html>

<html>

<head>

<meta  charset="UTF-8">

<!-- import CSS -->

<link  rel="stylesheet"  href="https://unpkg.com/element-ui/lib/theme-chalk/index.css">

<!-- 引入组件库 -->

<script  src="https://unpkg.com/element-ui/lib/index.js"></script>

<!-- 引入axios.js-->

<script  src="https://unpkg.com/axios/dist/axios.min.js"></script>

</head>

<body>

<div  id="piTable">

<template>

<el-table  ref="table"  :data="tableData">

<el-table-column  type="selection"></el-table-column>

<el-table-column  label="日期"  prop="date"></el-table-column>

<el-table-column  label="姓名"  prop="name"></el-table-column>

<el-table-column  label="部门"  prop="dept"></el-table-column>

<el-table-column  label="操作">

<template  slot-scope="props">

<el-button  type="primary"  @click="handleCheck(props.row)">查看</el-button>

</template>

</el-table-column>

<el-table-column  type="expand">

<template  slot-scope="props">

<div>这里是详情内容</div>

</template>

</el-table-column>

</el-table>

</template>

</div>

  

<div  id="piPage">

<template>

<div  class="block">

<el-pagination

@size-change="handleSizeChange"

@current-change="handleCurrentChange"

:current-page="currentPage"

:page-sizes="sizes"

:page-size="size"

layout="total, sizes, prev, pager, next, jumper"

:total="total">

</el-pagination>

</div>

</template>

  

</div>

</body>

<!-- import Vue before Element -->

<script  src="https://unpkg.com/vue/dist/vue.js"></script>

<!-- import JavaScript -->

<script  src="https://unpkg.com/element-ui@2.4.0/lib/index.js"></script>

<!-- import Vue Router -->

<script  src="https://unpkg.com/vue-router/dist/vue-router.js"></script>

<script>

var  ta = new  Vue({

el:'#piTable',

data:{tableData:[

{name:2,dept:22},

{name:2,dept:22},

{name:2,dept:22},

{name:2,dept:22},

{name:2,dept:22},

{name:2,dept:22}

]}

})

var  pa = new  Vue({

el:'#piPage',

data:{

currentPage:5,

sizes:[1,2,3,4],

size:1,

total:50

},

methods:{

handleSizeChange(){

console.log(ta.tableData[0].name);

console.log(pa.currentpage);

  

axios.post('/user', ta,{headers:{"Content-Type":  'application/json'},timeout:  1000})

.then(function (response) {

console.log(response);

})

.catch(function (error) {

console.log('错误');

console.log(error.response);

});

}

}

})

  

</script>

</html>
```
