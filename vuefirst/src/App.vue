<template>

  <div class="black-bg" v-if="modalOpen">
    <div class="white-bg">
      <h4>상세페이지임</h4>
      <p>상세페이지 내용임</p>
      <button @click="modalOpen=false">닫기</button>
    </div>
  </div>


  <div class="menu">
    <a v-for="m in menu" :key="m">{{m}}</a>
  </div>


  <div v-for="i in 3" :key="i">
    <h4 @click="modalOpen=true">{{products[i-1]}}</h4>
    <p>{{price[i-1]}} 만원</p>
    <button @click="increase(i-1)">허위매물신고</button> <span>신고수 : {{declareCount[i-1]}}</span>
  </div>
  
</template>

<script>

export default {
  name: 'App',
  data(){
    return {
        style1: 'color : blue;',
        products : ['역삼동원룸', '천호동원룸', '마포구원룸'],
        price : [70,80,90],
        menu : ['Home', 'Products', 'About'],
        declareCount : [0,0,0],
        img : ["./assets/room0.jpg","./assets/room1.jpg","./assets/room2.jpg"],
        modalOpen : false,
    }
  },

  methods : {
    increase(i){
      this.declareCount[i]++;
    }
  },

  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

.menu{
  background-color: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}

.menu a{
  color: white;
  padding:10px;
}

body{
  margin: 0;
}
div{
  box-sizing: border-box;
}
.black-bg{
  width: 100%; height: 100%;
  background-color: rgba(0,0,0,0.5);
  position: fixed;
  padding: 20px;
}
.white-bg{
  width: 100%;
  background-color: white;
  border-radius: 8px;
  padding: 20px;
}
</style>
