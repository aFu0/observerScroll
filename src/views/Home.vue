<template>
  <div class="classify">
    <loading v-show="loading"></loading>
    <observer @getData="getData">
      <section v-for="(item, i) in quantity" :key="i" @click="aaa" class="item">{{i}}</section>
    </observer>
  </div>
</template>

<script>
import observer from '@/components/observer/index'
// loading
import loading from '@/components/loading/index'
export default {
  name: 'classify',
  data () {
    return {
      // 数据条数
      quantity: 1,
      loading: false
    }
  },
  methods: {
    aaa () {
      console.log(123)
    },
    getData (callback) {
      window.setTimeout(() => {
        this.loading = false
        this.quantity += 10
        if (this.quantity >= 120) {
          // eslint-disable-next-line standard/no-callback-literal
          callback('close')
        } else {
          // eslint-disable-next-line standard/no-callback-literal
          callback(false)
        }
      }, 3000)
      this.loading = true
    }
  },
  components: {
    observer,
    loading
  }
}
</script>

<style scoped>
.classify {
  padding: 30px;
  box-sizing: border-box;
}
.goods-sum {
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
}
.goods-sum__goods {
  margin-bottom: 20px;
}
.item {
  width: 100%;
  height: 200px;
  margin-bottom: 30px;
  text-align: center;
  line-height: 200px;
  font-weight: 600;
  font-size: 40px;
  border-radius: 20px;
  box-shadow:0px 6px 20px 0px rgba(0,19,34,0.1);
}
</style>
