<template>
  <div class="wrapper" id="card">
    <IndicatorBase />
    <div class="lateral-lines">
      <div class="upper-lateral-line lateral-line">
        <svg
          width="26"
          height="206"
          viewBox="0 0 26 206"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path d="M26 1H8C4.13401 1 1 4.13401 1 8V206" stroke="#BCBCBC" />
          <path d="M1 186H5H11" stroke="#BCBCBC" />
        </svg>
      </div>
      <div class="lateral-burron">
        <a class="btn">
          <svg
            width="11"
            height="10"
            viewBox="0 0 11 10"
            fill="none"
            xmlns="http://www.w3.org/2000/svg"
          >
            <path d="M5.5 0V10" stroke="#BCBCBC" />
            <path d="M0 5L11 5" stroke="#BCBCBC" />
          </svg>
        </a>
      </div>
      <div class="lower-lateral-line lateral-line">
        <svg
          width="11"
          height="11"
          viewBox="0 0 11 11"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M11 10.5H8C4.13401 10.5 1 7.36599 1 3.5V0"
            stroke="#BCBCBC"
          />
        </svg>
      </div>
    </div>
    <LineIndicator />
  </div>
</template>

<script>
import IndicatorBase from "@/components/IndicatorBase.vue";
import LineIndicator from "@/components/LineIndicator.vue";

export default {
  name: "Card",
  components: {
    IndicatorBase,
    LineIndicator,
  },
};
</script>

<style lang="scss">
.wrapper {
  position: relative;
  background: blue;
  background: #fff;
  width: 309px;
  height: 468px;
  padding-bottom: 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: flex-start;
}

.lateral-lines {
  position: absolute;
  top: 148px;
  left: 20px;
}
.btn {
  margin: -5px -5px;
}
.lower-lateral-line {
  margin-top: -3px;
}
</style>
