<!-- home -->
<template>
  <div class="about-container">
    <div class="warpper">
      <h2>个人技能</h2>
      <div class="box">
        HTML<van-progress percentage="60" color="#f2826a"/>
      </div>
      <div class="box">
        CSS<van-progress percentage="70" color="#ee0a24" />
      </div>
      <div class="box">
        JavaScript<van-progress percentage="80"  pivot-color="#7232dd" color="linear-gradient(to right, #be99ff, #7232dd)"/>
      </div>
      <div class="box">
        Vue<van-progress percentage="90" color="#FF2869"/>
      </div>
      <div class="box">
        Webpack<van-progress percentage="90" />
      </div>
    </div>
  </div>
</template>

<script>
// 请求接口
import { getUserInfo } from '@/api/user.js'
import { mapGetters } from 'vuex'
export default {
  data() {
    return {
    }
  },
  computed: {
    ...mapGetters(['userName'])
  },
  mounted() {
    this.initData()
  },
  methods: {
    // 请求数据案例
    initData() {
      // 请求接口数据，仅作为展示，需要配置src->config下环境文件
      const params = { user: 'rain' }
      getUserInfo(params)
        .then(() => { })
        .catch(() => { })
    }
  }
}
</script>
<style lang="scss">
.about-container {
  background: #fff;
  height: 100vh;
  box-sizing: border-box;
  .warpper {
    padding: 50px 12px 12px 12px;
    .box {
      margin-bottom: 20px;
    }
  }
}
</style>
