<template>
    <div id="main">
        <div id="div_img">
            <img id="img" v-if="imgUrl != ''" :src=imgUrl alt="">
            <img id="gommette" v-else src="../assets/gommette.jpg">
        </div>
        <div id="div_button">
            <button id="button" type="button" class="btn btn-primary btn-lg" v-on:click="onClickButton">{{ msg }}</button>
        </div>
    </div>
</template>


<script>
export default {
    name: 'CatRoulette',
    props: {
        msg: String
    },
    data() {
        return {
            imgUrl: ""
        }
    },
    methods: {
        onClickButton() {
            fetch("https://api.thecatapi.com/v1/images/search")
                .then(res => res.json())
                .then((data) => {
                    console.log(data[0]);
                    this.imgUrl = data[0].url;
                })
        }
    }
}
</script>

<style>
#img {
    max-width: 350px;
    max-height: 100%;
    margin-left: 4%;
}

#main {
    height: 100%;
    width: 100%;

}

#div_button {
    position: absolute;
    top: 80vh;
    width: 50%;
    margin-left: 25%;
}

#div_img {
    position: absolute;
    width: 92%;
    height: fit-content;
    margin: 2%;
    align-self: center;
}

#gommette {
    height: 500px;
    width: 400px;
}
</style>