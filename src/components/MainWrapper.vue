<template>
  <main class="main">
    <div class="wrapper">
      <TimerComponent v-for="timer in timers" v-bind:key="timer.id" />
      <ControllerComponent v-on:addTimer="addNewTimer"/>
    </div>
  </main>
</template>

<script>
import TimerComponent from './Timer/TimerComponent.vue'
import ControllerComponent from './Controller/ControllerComponent.vue'

export default {
  name: 'MainWrapper',
  components: {
    TimerComponent,
    ControllerComponent
  },
  data(){
    return {
      timers: []
    }
  },
  methods: {
    addNewTimer () {
      this.timers.push({
        id: this.timers.length+1
      })
    }
  }
}
</script>
  
<style scoped>
  .main {
    display: flex;
    justify-content: center;    
    flex-wrap: wrap;
    column-gap: 5rem;
    row-gap: 4.5rem;
  }

  .wrapper {
    display: flex;
    justify-content: flex-start;    
    flex-wrap: wrap;
    column-gap: 5rem;
    row-gap: 4.5rem;
    width: 77.5rem;
  } 

  @media only screen and (max-width: 1024px){
    .wrapper {
      width: 77.5rem;
    }
  }

  @media only screen and (max-width: 768px){
    .wrapper {
      width: 50rem;
    }
  }

  @media only screen and (max-width: 500px){
    .wrapper {
      width: 22.5rem;
    }
  }
</style>
