<template>
    <div class="container">
        <div class="row">
            <div v-for="brother in brothers" v-bind:key="brother[0].username" class="col-lg-3">
                <div class="card mt-5">
                    <img class="card-img-top" v-bind:src="'data:image/jpeg;base64,'+brother[0].profile_url" alt="Card image cap">
                    <div class="card-body">
                        <h6 class="badge bg-info">@{{ brother[0].username }}</h6>
                        <p class="card-text">{{ brother[0].followed }}</p>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
    const axios = require("axios");

    export default {
        name: 'BbbSeguidores',
        props: {
            msg: String
        },
        data() {
            return {
                brothers: null
            };
        },
        methods: {
            getBrothers: function(){
                axios.get('http://192.168.1.10:8000/api').then(response => (this.brothers = response.data))
            }
        },
        beforeMount(){
            console.log('https://br.vuejs.org/v2/guide/instance.html');
        },
        mounted(){
            this.getBrothers();
        }
    }
</script>
