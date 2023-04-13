<template>
        <header>
            <h1>Get online to see the content</h1>
        </header>
        <div class="studentsList_offline">
            <div v-for="(cards,idx) in cards" :key="idx">
                <div class="offline_card">
                    <div class="card__image"></div>
                    <div class="card__content">
                        <h2></h2>
                        <p id="loading"></p>
                    </div>
                </div>
            </div>
        </div>
</template>
  
<script>

export default {
    name: 'HomeOffline',
    components: {
    },
    data() {
        return {
            cards:[0,1,2,3,4,5,6,7,8,9,10,11,12,13],
        }
    },
    mounted() {
    },
    methods: {
    },
}
</script>
<style scoped>

.offline_card {
    width: 225px;
    padding: 10px;
    background: #fff;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
    margin: 5px;
}

.card__content {
    padding: 20px;
}

@keyframes shine {
    to {
        background-position-x: -200%;
    }
}

.card__image,
#loading{
    background: linear-gradient(110deg, #ececec 8%, #f5f5f5 18%, #ececec 33%);
    border-radius: 5px;
    background-size: 200% 100%;
    animation: 1s shine linear infinite;
}

.card__image {
    height: 200px;
    border-bottom-left-radius: 0;
    border-bottom-right-radius: 0;
}

.card__content {
    padding: 20px;
}

#loading {
    height: 70px;
    width: 80%;
}


.studentsList_offline {
    display: flex;
    flex-wrap: wrap;
    flex-direction: row;
    justify-content: center;
}

header h1 {
    background-color: rgb(48, 50, 134);
    color: aliceblue;
    margin: 10px;
    text-align: center;
    box-sizing: content-box;
}

</style>
  