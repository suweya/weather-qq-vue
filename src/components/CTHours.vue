<template>
  <div class='container' id='ct-hours' :style="{width: `${width}px`}">
    <h2 id='title'>逐小时预报</h2>
    <a id='txt-source' href='http://www.weather.com.cn/' target='_blank'>数据来源于中国天气网</a>
    <div class='ct-page-ctrl'>
      <a href='javascript:;' id='btn-prev' class='btn' @click="prev"></a>
      <a href='javascript:;' id='btn-next' class='btn' @click="next"></a>
    </div>

    <div id='ct-weather' :style="{marginLeft: `${currentPosition}px`}">
      <ol>
        <li v-for='(item, idx) in hoursData' :key='idx' class='item'>
          <p class='txt-time'>{{item}}</p>
          <img src="../assets/01.png" alt="多云" title="多云" class="icon">
          <p class="txt-degree">24°</p>
        </li>
      </ol>
    </div>
  </div>
</template>

<script>

export default {
  name: 'CT-Hours',
  props: {
    count: {
      type: Number,
      default: 12,
      validator: function (value) {
        return value < 18
      }
    }
  },
  computed: {
    width () {
      return this.count * 40 + (this.count - 1) * 60
    }
  },
  created () {
    this.stepRange = [-(100 * 26) + this.width + 60, 0]
    this.stepDistance = (this.count - 1) * 100
  },
  data: function () {
    return {
      hoursData: ['09:00', '10:00', '11:00', '12:00', '13:00', '14:00', '15:00',
        '16:00', '17:00', '18:00', '18:35', '19:00', '20:00', '21:00', '22:00', '23:00', '明天',
        '01:00', '02:00', '03:00', '04:00', '05:00', '05:43', '06:00', '07:00', '08:00'],
      currentPosition: 0
    }
  },
  methods: {
    prev () {
      let temp = this.currentPosition + this.stepDistance
      this.currentPosition = (temp > this.stepRange[1] ? this.stepRange[1] : temp)
    },
    next () {
      let temp = this.currentPosition - this.stepDistance
      this.currentPosition = (temp < this.stepRange[0] ? this.stepRange[0] : temp)
    }
  }
}
</script>

<style lang='scss' scoped>
@import '../assets/variables.scss';

#ct-hours {
  height: 143px;
  background: #fff;
  border-radius: 10px;
  box-shadow: 0 0 14px 0 rgba($color: #000000, $alpha: 0.08);
  width: 1140px;
  padding: 20px 30px 27px;
  overflow: hidden;

  #title {
    font-size: 18px;
    color: $color-title;
    height: 21px;
    line-height: 21px;
    margin-bottom: 22px;
    float: left;
    margin-right: 10px;

    &:before {
      content: '';
      float: left;
      height: 7px;
      width: 7px;
      overflow: hidden;
      margin-right: 10px;
      background: $color-title;
      border-radius: 50%;
      margin-top: 8px;
    }
  }

  #txt-source {
    float: left;
    font-size: 12px;
    color: $color-title-second;
    height: 21px;
    line-height: 21px;
  }

  #btn-prev {
    background-image: url(../assets/sprite.png);
    background-position: -99px -154px;
    background-size: 234px 212px !important;
    margin-right: 8px;
  }

  #btn-next {
    background-image: url(../assets/sprite.png);
    background-position: -149px -154px;
    background-size: 234px 212px !important;
  }

  #ct-weather {
    clear: both;
    width: 4800px;
    transition: margin 1s ease-in-out;

    .item {
      float: left;
      width: 40px;
      margin-right: 60px;
      text-align: center;
      background-repeat: no-repeat;
      background-position: right;
      position: relative;

      .txt-time {
        font-size: 14px;
        color: #8a9baf;
        line-height: 14px;
        height: 14px;
        margin-bottom: 24px;
      }

      .icon {
        display: block;
        width: 30px;
        height: 30px;
        margin: 0 auto;
        margin-bottom: 18px;
      }

      .txt-degree {
        font-size: 18px;
        color: #384c78;
        line-height: 14px;
      }
    }
  }
}
</style>
