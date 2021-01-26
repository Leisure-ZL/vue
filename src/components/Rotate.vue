<template>
    <div>
        <div class="wrapper">
            <div class="ball"></div>
            <div class="stage">
                <div class="text">1111</div>
                <div class="text">1111</div>
                <div class="text">1111</div>
                <div class="text">1111</div>
            </div>
        </div>
    </div>
</template>

<script>
    export default{
        data() {

        },
        method: {

        }


    }


</script>

<style lang="less" scoped>
    .wrapper {
        width: 400px;
        height: 400px;
        margin: 200px;
        perspective: 800px;
        perspective-origin: 50% 50%;
        position: relative;
    }
    .stage {
        transform-style: preserve-3d;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate3d(-50%, -50%, 0);
    }
    .ball {
        width: 400px;
        height: 400px;
        border-radius: 50%;
        background-color: #ccc;
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate3d(-50%, -50%, 0);
        box-shadow: 0px 55px 45px -38px rgba(0, 0, 0, .3);
    }
    .ball::before {
        content: "";
        position: absolute;
        top: 1%;
        left: 5%;
        width: 90%;
        height: 90%;
        border-radius: 50%;
        background: -webkit-radial-gradient(50% 0px, circle, #ffffff, rgba(255, 255, 255, 0) 58%);
        z-index: 2;
    }
    .text {
        width: 200px;
        height: 100px;
        line-height: 50px;
        text-align: center;
        white-space: nowrap;
        animation: rotate 5s linear infinite;
        backface-visibility: hidden;
    }
    @keyframes rotate {
    from {
        transform: rotateY(0deg) translateZ(200px);
    }
    to {
        transform: rotateY(360deg) translateZ(200px);
    }
}

</style>