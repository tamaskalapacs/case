<template>
    <h3>{{question.name}} {{question.rating}}</h3>
</template>

<script>
//import ReplyList from './ReplyList'
import Vue from 'vue'

export default({

    name: 'Question',
    props:{
        question: Object
    },
    created(){
        Vue.add('question', 'rating', '0.0')
    }
})


</script>
