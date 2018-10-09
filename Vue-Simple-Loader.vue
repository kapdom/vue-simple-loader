<template>
    <div v-if="inProgress" class="vue-loader-container" :style="{ height: getHeight + 'px', width: getWidth +'px' }">
        <div class="vue-loader-box">
            <div class="circle-in"  :style="{ 'background-color': getFirstCircleColor }"></div>
            <div class="circle-out" :style="{ 'background-color': getSecondCircleColor }"></div>
        </div>
        <p class="vue-loader-text" :style="{ color: textColor }">{{text}}</p>
    </div>
</template>

<script>
export default {
    name: 'Vue-Simple-Loader',
    props: {
        // Display or hide loader
        inProgress: {
            type: Boolean,
            default: function(){
                return false
            }
        },
        // Text to display
        text: {
            type: String,
            default: function(){
                return '';
            }
        },
        // Text color
        textColor: {
            type: String,
        },
        // Html element to adjust loader size to other html element
        htmlElem: {
            type: HTMLElement,
            default: function(){
                return null;
            }
        },
        // Set a loader height
        setHeight: {
            type: Number,
        },
        // Set a loader width
        setWidth: {
            type: Number
        },
        // Set a circle colors
        setColor: {
            type: Object,
            default: function(){
                return null;
            }
        }
    },
    computed: {
        // Load height
        getHeight(){
            return this.htmlElem !== null ? this.htmlElem.offsetHeight : this.setHeight;
        },
        // Load width
        getWidth(){
            return this.htmlElem !== null ? this.htmlElem.offsetWidth : this.setWidth;
        },
        // Load first circle color
        getFirstCircleColor(){
            return this.setColor !== null ? this.setColor.firstCircle : null;
        },
        // Load second circle color
        getSecondCircleColor(){
            return this.setColor !== null ? this.setColor.secondCircle : null;
        }
    }
}

</script>

<style scoped>
    .vue-loader-container{
        position: relative;
        width:100%;
        height: 100%;
    }
    .vue-loader-box{
        width: 50%;
        height: 50%;
        position: relative;
        top: 50%;
        left: 50%;
        transform: translate(-50%,-50%);
    }
    .vue-loader-text{
        text-align: center;
        font-size: 50%;
        bottom: 20px;
        position: absolute;
        width: 100%;
        animation: pulse 2000ms infinite;
    }
    @-webkit-keyframes pulse {
        0% {
            transform: scale(1);
            opacity: 1;
        }
        100% {
            transform: scale(2);
            opacity: 0;
        }
    }

    @keyframes pulse {
        0% {
            transform: scale(1);
            opacity: 1;
        }
        100% {
            transform: scale(2);
            opacity: 0;
        }
    }
    .circle-in, .circle-out {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        opacity: 0.6;
        border-radius: 100%;
        background-color: #1eed5c;
        -webkit-animation: waving 2.0s infinite ease-in-out;
        animation: waving 2.0s infinite ease-in-out;
    }

    .circle-out {
        z-indexwebkit-animation-delay: -1.0s;
        animation-delay: -1.0s;
    }
    @-webkit-keyframes waving {
        0%, 100% {
            -webkit-transform: scale(0.0)
        }
        50% {
            -webkit-transform: scale(1.0)
        }
    }

    @keyframes waving {
        0%, 100% {
            transform: scale(0.0);
            -webkit-transform: scale(0.0);
        }
        50% {
            transform: scale(1.0);
            -webkit-transform: scale(1.0);
        }
    }
</style>