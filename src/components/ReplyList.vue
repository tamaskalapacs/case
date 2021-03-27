<template>
    <div>
        <h1>Reply List</h1>
        <table>
            <tr v-for="item in list" v-bind:key='item.id'>
                
                <td v-for="item2 in item.reply_questions" v-bind:key='item2.id'>{{item2.value}}</td>
                
            </tr>
        </table>

    </div>
</template>

<script>
import Vue from 'vue'
import axios from 'axios'
import VueAxios from 'vue-axios'

Vue.use(VueAxios, axios)

const access_token = "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJhdWQiOiIxIiwianRpIjoiMjM1ZTc2NzIwNmQ2N2U0YTBlOGQ3ZGQxY2Y0NDA3NDY4ZGFmZDQyMjg2NTYwMWY4MmVhOTZkMDIwNmRlNmFjN2E4ZmI3OWYxN2Q4NTM5OTMiLCJpYXQiOjE2MTU5ODI0MjQsIm5iZiI6MTYxNTk4MjQyNCwiZXhwIjoxNjQ3NTE4NDI0LCJzdWIiOiIyOTciLCJzY29wZXMiOlsiZ2V0LXJlcGxpZXMiLCJnZXQtbWVhc3VyZW1lbnQtZGV0YWlscyIsImdldC1vcmdhbml6YXRpb24tZGV0YWlscyJdfQ.mHS46k4UnRXXe9E5_IU9zEvZnz4mPR0ViLyg8fzuv0zqja3GwFn-bzKJQTWUJ4LAW2-lauVgCsr-T2hSx9jb7iSX7YigScYPmLUa_gj57GYQUoTFDi8oOaEys5CRsIR1qtEX0qP2ROYdfW-tW7hf9OtfKTb5ayylWzCa08bu2JPqDKwRQoKb0RK4gdcMYZOb6gmkKF3Esy1wzxx4ahpWyplaYcAWCYTb0vijPGIm0-9JZQBydSyg7xsTtOdUAHKsl7luPZoLPYPaauwIwZObQvB5WfdIiwEvS4BND_Dw-y_2FS7DGscak1YeakPMSQgVgqnt-T2v-H0TaW6bpLg30BpEkFe1qKZxs60yvppAAOhyob-EM8mYZUx3Lh8fJMJor5UC1vKE9nFft4d-Qc0fShRZ5cwE-7DNM4UUyPnK-d_PxpE9khJlSFmw7LeODnbk5SAjVMp8UHI7_sJ1gJh54zcfC33k2Sj0ec1OFotlZ_3CPZyGbz0XM5-mUHgrrjeZUzFyXEOBwr6Ho_Cf49AwqxUhjeSgdCpXu6eEazYi1L5vqYiyMZMalS9Zu7MncDnEKtET5FPdf8bqQE0EAp0nBXqWPIyF8FSPG-XjCFoawl3dFw3zybu41NKxRlxX4FxptapK0SF6Qwy2Ld2_kl-zqiVxXa582fZuYbK3DXj5rQI"

export default{
    name: "ReplyList",
    data(){
        return{list:undefined}
    },
    mounted(){

        Vue.axios.get('https://business.stagingtalenthub.com/api/measurements/ab8b76b28aeb494992c47466fea7e49e/replies/bulk', {
            headers: {

                'Accept': 'application/json',
                'Authorization': `Bearer ${access_token}`
                
            }
        })
        .then((resp)=>{
            this.list = resp.data.data
            console.warn(resp.data.data)
        })
        .catch((error => {
            console.error(error)
        }))
    }
}
</script>