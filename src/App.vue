<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <vue-ztree :treeNodes="treeNodes" @onClick="handleTreeClick" :check="check" @onCheck="handleCheck"/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import VueZtree from "ztree-for-vue";
const nodes= [
	{name: '父节点1',
    id:0,
     children: [
		{name: '子节点1',
    id:1},
		{name: '子节点2',id:2,children:[
      {name:'子节点3',id:3}
    ]}
	]}
];
export default {
  name: "app",
  data() {
    return {
      treeNodes: [],
      check:{
        enable:true
      }
    };
  },
  components: {
    // HelloWorld,
    VueZtree
  },
  methods:{
    handleTreeClick(event,treeId,treeNode) {
      console.log(event,treeId,treeNode)
    },
    handleCheck(event,treeId,treeNode) {
      console.log(event,treeId,treeNode);
    }
  },
  mounted() {
    setTimeout(()=>{
      this.treeNodes = nodes;
    },2000)
  }
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
