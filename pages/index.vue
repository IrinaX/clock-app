<template>
  <div class="container">
    <div class="time">
      <v-number v-for="(val,key) in d_time"
                :key="key"
                :class="'number_'+val"
      />
    </div>
  </div>
</template>

<script>
import VNumber from '../components/VNumber'
import moment from 'moment'

export default {
  components: {
    VNumber
  },
  data () {
    return {
      d_time: {
        H: moment().format('HH:mm:ss')[0],
        h: moment().format('HH:mm:ss')[1],
        M: moment().format('HH:mm:ss')[3],
        m: moment().format('HH:mm:ss')[4],
        S: moment().format('HH:mm:ss')[6],
        s: moment().format('HH:mm:ss')[7],
      },
      d_intervalId:null,
    }
  },
  mounted () {
    moment.locale('ru');
    this.d_intervalId = setInterval(this.updateTime, 1000);
  },
  beforeDestroy () {
    clearInterval(this.d_intervalId);
  },

  methods: {
    updateTime () {
      this.d_time = {
        H: moment().format('HH:mm:ss')[0],
        h: moment().format('HH:mm:ss')[1],
        M: moment().format('HH:mm:ss')[3],
        m: moment().format('HH:mm:ss')[4],
        S: moment().format('HH:mm:ss')[6],
        s: moment().format('HH:mm:ss')[7],
      }
    },
  },
}
</script>

<style lang="scss">
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.time {
  display: flex;
}
</style>
