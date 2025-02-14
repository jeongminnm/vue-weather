<template>
    <div class="page">페이지 컴포넌트 입니다.</div>
</template>



<script>
import MAINPAGE from "@components/organisms/index.vue"
export default {
    components: {
        MAINPAGE,
    },
    data()  {
        return {};
    },
};
</script>

<style lang="scss" scoped>
@import "@assets/styles/main.scss";

reference
.page {
    width: 100vw;
    height: 100vh;

    background-color: $color-white-100;
}
</style>