<template>
  <div id="ct-living-index">
    <div class="ct-page-ctrl">
      <a href="javascript:;" id="btn-prev" class="btn" @click="prev"></a>
      <a href="javascript:;" id="btn-next" class="btn" @click="next"></a>
    </div>
    <h2 id="title">生活指数</h2>
    <div id="ct-pages">
      <div id="ct-content" :style="{marginLeft : marginLeft + 'px'}">
        <ul :id="`ls-living${index}`" class="page" v-for="(item, index) in data" :key="index">
          <li class="item" v-for="(obj, idx) in item" :key="idx" :class="idx%2 === 0 ? 'odd' : 'even'">
            <div class="ct-sub">
              <i class="icon" :class="obj.iconCls"></i>
              <p class="content">{{obj.label}}</p>
            </div>
            <div class="ct-detail">
              <div class="detail">{{obj.content}}</div>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      data: [
        [
          {
            label: '穿衣 热',
            content: '天气热，建议着短裙、短裤、短薄外套、T恤等夏季服装。',
            iconCls: 'icon_chuanyi_hot'
          },
          {
            label: '雨伞 不带伞',
            content: '天气较好，不会降水，因此您可放心出门，无须带雨伞。',
            iconCls: 'icon_chuanyi_hot'
          },
          {
            label: '穿衣 热',
            content: '天气热，建议着短裙、短裤、短薄外套、T恤等夏季服装。',
            iconCls: 'icon_chuanyi_hot'
          },
          {
            label: '穿衣 热',
            content: '天气热，建议着短裙、短裤、短薄外套、T恤等夏季服装。',
            iconCls: 'icon_chuanyi_hot'
          },
          {
            label: '穿衣 热',
            content: '天气热，建议着短裙、短裤、短薄外套、T恤等夏季服装。',
            iconCls: 'icon_chuanyi_hot'
          },
          {
            label: '穿衣 热',
            content: '天气热，建议着短裙、短裤、短薄外套、T恤等夏季服装。',
            iconCls: 'icon_chuanyi_hot'
          }
        ],
        [
          {
            label: '穿衣 热',
            content: '天气热，建议着短裙、短裤、短薄外套、T恤等夏季服装。',
            iconCls: 'icon_chuanyi_hot'
          },
          {
            label: '雨伞 不带伞',
            content: '天气较好，不会降水，因此您可放心出门，无须带雨伞。',
            iconCls: 'icon_chuanyi_hot'
          },
          {
            label: '穿衣 热',
            content: '天气热，建议着短裙、短裤、短薄外套、T恤等夏季服装。',
            iconCls: 'icon_chuanyi_hot'
          },
          {
            label: '穿衣 热',
            content: '天气热，建议着短裙、短裤、短薄外套、T恤等夏季服装。',
            iconCls: 'icon_chuanyi_hot'
          },
          {
            label: '穿衣 热',
            content: '天气热，建议着短裙、短裤、短薄外套、T恤等夏季服装。',
            iconCls: 'icon_chuanyi_hot'
          },
          {
            label: '穿衣 热',
            content: '天气热，建议着短裙、短裤、短薄外套、T恤等夏季服装。',
            iconCls: 'icon_chuanyi_hot'
          }
        ]
      ],
      marginLeft: 0
    }
  },
  methods: {
    prev() {
      if (this.marginLeft < 0) {
        this.marginLeft = 0
      }
    },
    next() {
      if (this.marginLeft >= 0) {
        this.marginLeft = -440
      }
    }
  }
}
</script>

<style lang="scss" scoped>
#ct-living-index {
  float: right;
  width: 430px;
  position: relative;

  .ct-page-ctrl {
    float: right;
    margin-top: 7px;

    .btn {
      float: left;
      z-index: 2;
      width: 23px;
      height: 23px;
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
  }

  #title {
    float: left;
    font-size: 18px;
    color: #344665;
    height: 21px;
    margin-bottom: 6px;
    margin-top: 6px;

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

  #ct-pages {
    clear: both;
    overflow: hidden;
    position: relative;
    width: 440px;
    height: 470px;
    margin-left: -5px;
    margin-top: 18px;

    #ct-content {
      width: 890px;
      transition: margin 1s ease-in-out;
    }

    .page {
      width: 440px;
      float: left;
    }

    .item {
      height: 140px;
      width: 200px;
      background: #fff;
      box-shadow: 0 0 14px 0 rgba($color: #000000, $alpha: 0.08);
      border-radius: 10px;
      float: left;
      text-align: center;
      overflow: hidden;
      margin-bottom: 20px;
      margin-left: 10px;

      &.odd {
        margin-right: 14px;
      }

      &:hover .ct-sub {
        margin-top: -140px;
      }
    }

    .ct-sub {
      height: 102px;
      width: 100%;
      padding-top: 38px;
      transition: margin 0.5s ease-in-out;
    }

    .icon {
      height: 34px;
      width: 34px;
      display: block;
      margin: 0 auto 12px;
    }

    .icon_chuanyi_hot {
      background-image: url(../assets/sprite.png);
      background-position: -80px -37px;
      background-size: 234px 212px !important;
    }

    .content {
      font-size: 16px;
      color: #384c78;
      line-height: 22px;
    }

    .ct-detail {
      height: 100%;
      width: 160px;
      padding: 0 20px;
      display: table;
      overflow: hidden;

      .detail {
        vertical-align: middle;
        text-align: left;
        text-align: justify;
        text-justify: inter-ideograph;
        display: table-cell;
        font-size: 13px;
        color: #384c78;
        line-height: 1.5;
        overflow: hidden;
        text-overflow: ellipsis;
        -webkit-line-clamp: 5;
        -webkit-box-orient: vertical;
      }
    }
  }
}
</style>
