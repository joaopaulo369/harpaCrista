<script setup>
defineProps({
    hino: Object
})
// console.log(hino)
</script>

<template>

    <div class="card my-3 roboto-serif cardhino">
        <div class="card-body text-center">
            <h4 class="card-title">{{ hino.hino }}</h4>
            <!-- <h6 class="card-subtitle mb-2 text-body-secondary">Card subtitle</h6> -->
            <span v-for="(verso, index) in hino.verses" :key="index">
                <p v-html="verso"></p>
                <div class="mb-3">
                    <strong v-if="index <= 1" v-html="hino.coro"></strong>
                </div>
            </span>
        </div>
    </div>

</template>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Raleway:ital,wght@0,100..900;1,100..900&family=Roboto+Serif:ital,opsz,wght@0,8..144,100..900;1,8..144,100..900&family=Source+Serif+4:ital,opsz,wght@0,8..60,200..900;1,8..60,200..900&display=swap');

.roboto-serif {
  font-family: "Roboto Serif", serif;
  font-optical-sizing: auto;
  font-style: normal;
}

.cardhino{
    cursor: pointer;
}

</style>