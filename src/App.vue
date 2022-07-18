<template>
    <div id="app">
        <div class="title__abs"><div class="title">AirPods Max</div></div>
        <div class="section_35">
            <div class="header">
                <div class="header__item img"><img src="./assets/header/logo.png" alt="logo apple"></div>
                <div class="header__item header__text">IPHONE</div>
            </div>
            <div class="content content_1">
                <div class="content_1__text">
                    <div>AirPods Max combine a custom acoustic design, H1 chips, and advanced software to power computational audio for a breakthrough listening experience with Adaptive EQ, Active Noise Cancellation, Transparency mode, and spatial audio.</div>
                </div>
                <div class="content_1__img">
                    <img src="./assets/content/Product_Photo_1.png" alt="product photo 1">
                </div>
            </div>
        </div>
        <div class="section_30">
            <div class="header">
                <div class="header__item">IPAD</div>
            </div>
            <div class="content content_2">
                <div class="block_1">
                    <div style="width: 75%">
                        <img src="./assets/content/Product_Photo_2.png" alt="product photo 2" style="width: 80%">
                    </div>
                    <div class="colors" style="width: 25%">
                        <div v-for="(color, index) in colors" :key="index" class="colors_rounded" :class="{colors_active: color.isActive}" :style="{backgroundColor: color.color}" @click="changeActiveColor(index)"></div>
                    </div>
                </div>

                <div class="block_2">
                    <img src="./assets/content/Product_Photo_3.png" alt="product photo 3">
                    <div class="border"></div>
                </div>
            </div>
        </div>
        <div class="section_35">
            <div class="header">
                <div class="header__item header__text">MUSIC</div>
                <div class="header__item img"><img src="./assets/header/Shop.png" alt="logo shop"></div>
            </div>
            <div class="content content_3">
                <img src="./assets/content/Product_Photo_4.png" alt="product photo 4">
                <div class="content_3_bottom">
                    <div class="text">
                        From the canopy to the ear cushions, every part of AirPods Max is carefully crafted to provide exceptional acoustic performance for each user. The breathable knit mesh canopy, spanning the headband, is made to distribute weight and reduce on-head pressure.
                    </div>
                    <div class="arrow">
                        <div class="border">
                            <img src="./assets/content/Arrow.png" alt="arrow">
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'App',

    data() {
        return {
            colors: [
                {
                    isActive: true,
                    color: "#DA4A42"
                },
                {
                    isActive: false,
                    color: "#374F69"
                },
                {
                    isActive: false,
                    color: "#788574"
                },
                {
                    isActive: false,
                    color: "#353538"
                },
                {
                    isActive: false,
                    color: "#F2F2F2"
                },
            ]
        }
    },

    methods: {
        changeActiveColor: function(index) {
            // reset
            this.colors.forEach(color => {
                color.isActive = false
            })
            // set
            this.colors[index].isActive = true
        }
    },
}
</script>

<style lang="scss">
$main_color: #353538;
$background: #DEDEDE;

#app {
    width: 100vw;
    height: 100vh;
    display: flex;
    background-color: $background;
    overflow: hidden;
}

.title__abs {
    position: absolute;
    width: 100px;
    bottom: 5%;
    left: 22%;
}

.title {
    position: relative;
    z-index: 100;
    font-family: 'MonumentExtended';
    font-size: 72px;
    color: $main_color;
}
.section {
    &_35 {
        width: 35%;
        height: 100%;
    }
    &_30 {
        width: 30%;
        height: 100%;
    }
}

.header {
    display: flex;
    align-items: center;
    font-family: 'MonumentExtended';
    color: $main_color;
    font-weight: 400;
    font-size: 24px;
    line-height: 29px;
    height: 12%;
    z-index: 10;
    position: relative;
    background-color: $background;

    &__item {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 100%;
        border: 1px solid $main_color;
        border-top-style: none;
        border-left-style: none;
        width: 100%;
    }
    & .img {
        width: 18%;
    }
    &__text {
        width: 82%;
    }
}

.content {
    height: 88%;

    &_1 {

        &__text {
            font-family: 'Antonio';
            font-weight: 400;
            font-size: 14px;
            line-height: 18px;
            display: flex;
            align-items: center;
            justify-content: center;
            color: $main_color;
            width: 100%;
            height: 20%;
    
            & div {
                width: 64%;
            }
        }
    
        &__img {
            height: 80%;
            & img {
                height: 100%;
            }
        }
    }

    &_2 {
        position: relative;

        & .block_1 {
            display: flex;

            & .colors {
                display: flex;
                flex-direction: column;
                align-items: center;
                justify-content: center;
                gap: 25px;
                margin-top: -15%;
                margin-left: -5%;

                &_rounded {
                    height: 35px;
                    width: 35px;
                    border-radius: 50%;
                    cursor: pointer;
                }

                &_active {
                    animation: colorsAnimation 100ms forwards;
                }
            }
        }

        & .block_2 {
            height: 52%;
            position: absolute;
            left: 15%;
            top: 45%;

            img {
                z-index: 2;
                position: relative;
            }

            & .border {
                position: absolute;
                width: 100%;
                height: 100%;
                top: 0;
                border: 1px solid #353538;
                transform: translate(5%, 5%);
            }
        }
    }

    &_3 {
        & img {
            width: 100%;
            transform: translateY(-10%);
        }

        &_bottom {
            display: flex;
            transform: translateY(-38%);
            background-color: #B6B8B8;
            height: 25%;

            & .text {
                width: 75%;
                padding: 0 10% 0 10%;
                margin-top: -2.5%;
                display: flex;
                justify-content: center;
                align-items: center;
                color: #FAFAFA;
                font-family: 'Antonio';
                font-weight: 400;
                font-size: 14px;
                line-height: 18px;
            }

            & .arrow {
                width: 25%;
                margin-top: -2.5%;
                display: flex;
                justify-content: center;
                align-items: center;

                & .border {
                    width: 20px;
                    height: 20px;
                    outline: 1px solid #fafafa;
                    outline-offset: 25px;
                    border-radius: 50%;
                }
            }
        }
    }
}

@keyframes colorsAnimation {
    from {
        outline: none;
    }
    to {
        outline: 1px solid #353538;
        outline-offset: 10px;
    }
}
</style>
