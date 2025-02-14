<template>
    <div class="graph">
    <div class="graph__outer"></div>
    <div class="graph__inner"></div>
    <div class="graph__middle"></div>
    <span class="graph__value">그래프 값</span>
    <span class="graph__name">그래프 이름</span>
    </div>
</template>

<script>
export default {
    data () {      
        return {};
    },
};
</script>

<style lang="scss" scoped>
@import "../../assets/styles/main.scss";
.graph {
    position: relative;

    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;

    width: 180px;
    height: 180px;

    border-radius: 50%;

    &__outer{
        position: absolute;

        width: 160px;
        height: 160px;

        background-color: $color-white-000;
        border-radius: 50%;
    }
    &__inner {
        position: absolute;
        z-index: 2;

        width: 124px;
        height: 124px;

        background-color: $color-white-100;
        border-radius: 50%;

        box-shadow: 0px 0px 10px 0px inset rgb(206, 206, 206);
    }
    &__middle{
        position: absolute;

        width: 160px;
        height: 160px;
        border-radius: 50%;

    }
    &__value{
        position: absolute;
        z-index: 3;

        font-size: 24px;

    }
    &__name{
        position: absolute;
        bottom: -24px;

        font-weight: 300;
    }
}

</style>