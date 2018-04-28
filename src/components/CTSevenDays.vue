<template>
  <div id="ct-7-days">
    <a id="link-15" href="http://www.weather.com.cn/weather15d/101230201.shtml" target="_blank">15日天气预报</a>
    <h2 id="title">7日天气预报</h2>
    <div id="ct-weather">
      <ol>
        <li class="item" :class="{first: idx === 0, second: idx === 1}" v-for="(item, idx) in days" :key="idx">
          <p class="day">{{item.label}}</p>
          <p class="date">{{item.date}}</p>
          <div class="ct-daytime">
            <p class="weather">{{item.weather}}</p>
            <img class="icon" src="../assets/01.png" alt="阴" title="阴">
          </div>
          <div class="ct-night">
            <img class="icon" src="../assets/01.png" alt="阴" title="阴">
            <p class="weather">{{item.weather}}</p>
          </div>
          <p class="wind">东北风 4级</p>
        </li>
      </ol>

      <div id="chart-days"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CT-Seven-Days',
  data: function() {
    return {
      days: [
        {
          label: '昨天',
          date: '04月27日',
          weather: '多云'
        },
        {
          label: '今天',
          date: '04月28日',
          weather: '多云'
        },
        {
          label: '明天',
          date: '04月29日',
          weather: '多云'
        },
        {
          label: '后天',
          date: '04月30日',
          weather: '多云'
        },
        {
          label: '周二',
          date: '05月01日',
          weather: '多云'
        },
        {
          label: '周三',
          date: '05月02日',
          weather: '多云'
        },
        {
          label: '周四',
          date: '05月03日',
          weather: '多云'
        },
        {
          label: '周五',
          date: '05月04日',
          weather: '多云'
        }
      ]
    }
  }
}
</script>

<style lang="scss" scoped>
#ct-7-days {
  float: left;
  width: 740px;
  height: 492px;
  padding: 20px 0 0;
  border-radius: 10px;
  background-color: #fff;
  box-shadow: 0 0 14px 0 rgba($color: #000000, $alpha: 0.08);

  #link-15 {
    float: right;
    background: #f8faff;
    border: 1px solid #dce5f0;
    border-radius: 37px;
    font-size: 12px;
    color: #384c78;
    line-height: 26px;
    height: 26px;
    width: 100px;
    text-align: center;
    margin-right: 30px;
  }

  #title {
    font-size: 18px;
    color: #344665;
    line-height: 25px;
    height: 25px;
    margin-bottom: 18px;
    margin-left: 30px;
    text-align: left;

    &:before {
      content: '';
      float: left;
      height: 7px;
      width: 7px;
      overflow: hidden;
      margin-right: 10px;
      background: #344665;
      border-radius: 50%;
      margin-top: 8px;
    }
  }

  #ct-weather {
    overflow: hidden;
    position: relative;

    .item {
      width: 92px;
      text-align: center;
      float: left;
      background-repeat: no-repeat;
      background-position: right;
      position: relative;
      padding: 11px 0 25px;

      .day {
        font-size: 14px;
        color: #384c78;
        margin-bottom: 12px;
        height: 14px;
        line-height: 14px;
      }

      .date {
        font-size: 12px;
        color: #8a9baf;
        margin-bottom: 30px;
        height: 12px;
        line-height: 12px;
      }

      &.first {
        .day,
        .date,
        .weather,
        .wind {
          color: #c2c2c2;
        }

        .icon {
          opacity: 0.3;
        }
      }

      .weather {
        margin-bottom: 20px;
        font-size: 14px;
        color: #384c78;
        line-height: 14px;
        height: 14px;
      }

      .icon {
        display: inline-block;
        width: 30px;
        height: 30px;
      }

      .ct-night {
        margin-top: 174px;
        margin-bottom: 24px;

        .icon {
          margin-bottom: 20px;
        }
      }

      .wind {
        font-size: 12px;
        color: #8a9baf;
        line-height: 12px;
        height: 12px;
      }
    }

    #chart-days {
      width: 740px;
      height: 174px;
      position: absolute;
      top: 145px;
    }
  }
}
</style>
