<template>
    <div>
        <div class="container">
            <div v-for="(channel, index) in channels" :key="index" class="card m-4">
                <div class="card-body">
                    <h5 class="card-title">{{ channel }}</h5>
                    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                    <a href="#" class="btn btn-primary">Go somewhere</a>
                </div>
            </div>
        </div>
    </div>
    
</template>


<script>
import axios from 'axios';
// import channel from '../../components/channel';

export default {
    async asyncData ({ params, error }) {
        return axios.get(`http://localhost:8000/api/channels/`)
        .then((res) => {
            return { 
                channels: res.data 
            }
        })
        .catch((e) => {
            error({ statusCode: 404, message: 'Post not found' })
        })
    },
    data() {
        return {
            channels: []
        };
    },
    head() {
        return {
            title: 'List of Channels',
            meta: [
                {
                    hid: 'description',
                    name: 'description',
                    content: 'The forum app for any organization'
                }
            ]
        };
    }
};
</script>

<style>

</style>