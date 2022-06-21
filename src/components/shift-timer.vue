<template>
  <div>
    <h1 v-if="startedShift" class="title">czas do końca szychty</h1>
    <h1 v-else class="title">czas do początku szychty</h1>
    <slot :hour="hour" :min="min" :sec="sec"></slot>
    <time>{{ hour }}<span>h</span> {{ min }}<span>m</span> {{ sec }}<span>s</span></time>
  </div>
</template>

<script>
const now = new Date(2022, 6, 21, 21, 31)
const today = now.getHours() > 20

const startTime = new Date(now)
startTime.setHours(21, 30)

const endTime = new Date(now)
endTime.setHours(5, 45)

const startedShift = now <= endTime || now >= startTime

export default {
  name: "shift-timer",
  props: {
    startedShift: {
      type: Boolean,
      default: startedShift
    },
    endDate: {
      type: Date,
      default() {
        const endDate = new Date(now)

        if (startedShift) {
          endDate.setHours(5, 45)
          if (!today) endDate.setDate(endDate.getDate() + 1)
        } else {
          endDate.setHours(21, 30)
        }
        console.log(startedShift)
        return endDate
      }
    },
    negative: {
      type: Boolean,
      default: false
    }
  },
  data() {
    return {
      now: new Date(Date.now()),
      timer: null
    }
  },
  computed: {
    hour() {
      let h = Math.trunc((this.endDate - this.now) / 1000 / 3600);
      return h > 9 ? h : '0' + h;
    },
    min() {
      let m = Math.trunc((this.endDate - this.now) / 1000 / 60) % 60;
      return m > 9 ? m : '0' + m;
    },
    sec() {
      let s = Math.trunc((this.endDate - this.now) / 1000) % 60
      return s > 9 ? s : '0' + s;
    }
  },
  watch: {
    endDate: {
      immediate: true,
      handler(newVal) {
        if (this.timer) {
          clearInterval(this.timer)
        }
        this.timer = setInterval(() => {
          this.now = new Date()
          if (this.negative)
            return
          if (this.now > newVal) {
            this.now = newVal
            this.$emit('endTime')
            clearInterval(this.timer)
          }
        }, 1000)
      }
    }
  },
  beforeUnmount() {
    clearInterval(this.timer)
  }
}
</script>

<style scoped>
div {
  color: #FFF;
  text-align: center;
}

h1 {
  font-size: 40px;
  font-weight: lighter;
  margin-bottom: 0;
}

time {
  font-size: 100px;
}

span {
  font-size: 30px;
}
</style>