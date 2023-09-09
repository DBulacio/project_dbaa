<template>
    <div :style="{backgroundColor: this.color}" class="pop-up">{{this.text}}</div>
</template>

<script>

export default {
    props: ["color","text"]
}

</script>

<style scoped>
    .pop-up{
    text-align: center;
}
</style>