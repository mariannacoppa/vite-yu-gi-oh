<script>
export default {
    props: {
        card: Object
    }
}
</script>
<template lang="">
    <div class="col-20">
        <div class="card p-1">
            <img :src="card?.card_images[0].image_url" alt="">
            <div class="card-body">
                <h6>
                    {{ card?.name }}
                </h6>
            </div>
        </div>
    </div>
</template>
<style lang="scss" scoped>
.row-list {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}
.col-20 {
    width: calc(100% / 5);
}
.card {
    background-color: burlywood;
    margin: 10px;
    img {
        max-width: 100%;
    }
}
</style>