<template>
    <div class="timer-wrapper">

        <h3 class="timer__time">
            <span>{{ hours<10?"0"+hours:hours }}:</span>
            <span>{{ minutes<10?"0"+minutes:minutes }}:</span>
            <span>{{ seconds<10?"0"+seconds:seconds }}</span>
        </h3>

        <div class="timer__controller">
            <div class="timer__controller__start-btn" v-on:click="start" v-if="!this.showPause"></div>
            <div class="timer__controller__pause-btn" v-on:click="pause" v-if="this.showPause"></div>
            <div class="timer__controller__clear-btn" v-on:click="reset"></div>
        </div>
    </div>
</template>

<script>

export default {
    name: 'TimerComponent',
    data() {
        return {
            interval: null,
            showPause: false,
            seconds: 0,
            minutes: 0,
            hours: 0
        }  
    },
    methods: {
        start() {
            this.showPause = true
            this.interval = setInterval(() => {
                this.seconds++

                if (this.seconds===60) {
                    this.minutes++
                    this.seconds=0
                }

                if (this.minutes===60) {
                    this.hours++
                    this.minutes=0
                }
            }, 1000)
        },
        pause() {
            if (this.interval) clearInterval(this.interval)
            this.showPause = false
        },
        reset() {
            if (this.interval) clearInterval(this.interval) 
            this.showPause = false
            this.seconds=0
            this.minutes=0
            this.hours=0
        }
    }
}
</script>


<style scoped>
    .timer-wrapper {
        
        width: 22.5rem;
        height: 12rem;
        
        background: #696969;
    
        position: relative;


    }
    .timer__time {
        height: 6rem;
        line-height: 6rem;
    }

    .timer__controller {
        height: 6rem;

        display: flex;
        justify-content: center;
        align-items: center;
        column-gap: 5.2rem;
    }

    .timer__controller__pause-btn {
        width: 1.2rem;
        height: 2rem;

        position: relative;
        cursor: pointer;
    }

    .timer__controller__pause-btn::after {
        content: '';

        position: absolute;
        left: 0;
        top: 0;

        height: 100%;
        width: .3rem;
        background: #9E9E9E;
    }

    .timer__controller__pause-btn::before {
        content: '';

        position: absolute;
        right: 0;
        top: 0;

        height: 100%;
        width: .3rem;
        background: #9E9E9E;
    }

    .timer__controller__clear-btn {
        width: 2rem;
        height: 2rem;
        background: #9E9E9E;

        cursor: pointer;
    }

    .timer__controller__start-btn {
        
        width: 1.7rem;
        height: 2rem;
        
        border-style: solid;
        border-width: 10px 0px 10px 17px;
        border-color: transparent transparent transparent #9E9E9E;
        
        cursor: pointer;
    }



    .timer-wrapper::before {

        content: '';
        
        position: absolute;
        left: 0;
        top: 50%;
        
        width: 100%;
        border: 1px solid #9E9E9E;

        transform: translateY(-50%);
    }

</style>