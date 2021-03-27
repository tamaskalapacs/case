<template>
  <div id="app">
    <Chart />
    <QuestionList /> 
    <ReplyList />
    
    
 </div>
</template>

<script>
import QuestionList from './components/QuestionList'
import ReplyList from './components/ReplyList'
import Chart from './components/Chart'


export default {
  name: 'App',
  components: {
      QuestionList,
      ReplyList,
      Chart

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
  margin-top: 60px;
}
</style>
