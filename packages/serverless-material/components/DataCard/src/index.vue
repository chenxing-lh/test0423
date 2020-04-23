<template>
  <div
    class="statistics-box shadow"
    :style="{backgroundColor: item.bgColor,height: item.height,width: item.width}"
  >
    <icon-font :icon="item.icon" />
    <div class="box-inner">
      <p class="count">{{ item.value }}</p>
      <p>{{ item.label }}</p>
    </div>
    <div
      class="update-time"
      v-if="item.updateTime"
    >
      <span>更新时间：{{ item.updateTime }}</span>
    </div>
  </div>
</template>

<script>
import IconFont from "./icon-font";
export default {
  components: {
    IconFont
  },
  props: {
    item: {
      type: Object,
      default: () => ({
        height: "170px",
        width: "270px",
        bgColor: "#e2357c",
        icon: "iconup",
        value: "$ 120,690",
        label: "总收入",
        updateTime: "13:00"
      })
    }
  },
  data() {
    return {};
  }
};
</script>

<style lang="less">
* {
  margin: 0;
}
@import url("//at.alicdn.com/t/font_1261976_pwsuu09jfo.css");
.shadow {
  box-shadow: 0 2px 12px rgba(0, 0, 0, 0.1);
}

.card-box {
  margin-bottom: 20px;
}
.statistics-box {
  border-radius: 6px;
  color: #fff;
  padding: 30px 25px 15px;
  font-size: 14px;
  position: relative;
  min-height: 160px;
  margin-bottom: 10px;
  display: flex;

  i {
    font-size: 34px;
    margin: 4px 15px 0 0;
  }

  .box-inner {
    display: inline-block;
    font-size: 16px;

    .count {
      font-size: 24px;
    }
  }

  .update-time {
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 50px;
    line-height: 50px;
    background: rgba(0, 0, 0, 0.1);
    span {
      padding-left: 30px;
    }
  }
}
</style>