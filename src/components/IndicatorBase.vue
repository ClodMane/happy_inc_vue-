<template>
  <div class="indicator-base">
    <div class="card-icon">
      <svg
        width="39"
        height="47"
        viewBox="0 0 39 47"
        fill="currentColor"
        xmlns="http://www.w3.org/2000/svg"
      >
        <path
          d="M2.61163 -0.000460072C1.16897 -0.000460072 -0.000366211 1.16887 -0.000366211 2.61154C-0.000366211 2.98087 0.0783004 3.33154 0.216967 3.64887C0.455634 4.19287 0.8343 5.31421 0.8343 6.29554V44.8169C0.8343 45.7982 1.62897 46.5982 2.61163 46.5982C3.59297 46.5982 4.39297 45.7982 4.39297 44.8169V6.29554C4.39297 5.31421 4.7703 4.19287 5.00497 3.64887C5.14497 3.33154 5.2223 2.98087 5.2223 2.61154C5.2263 1.17287 4.0543 -0.000460072 2.61163 -0.000460072Z"
          fill="currentColor"
        />
        <path
          d="M31.5997 18.2006C31.2397 18.6912 31.2437 19.3512 31.6104 19.7979C33.5637 22.1659 35.5744 24.1086 37.4731 25.6579C39.1464 27.0246 36.9651 28.0206 36.4757 28.2286C26.5157 32.4832 16.5637 23.5819 6.61041 26.2926V5.27923C16.5797 2.56723 26.5477 11.5072 36.5171 7.1979C37.0037 6.9899 37.4477 7.04057 37.6624 7.36857C37.8757 7.6939 37.8224 8.2539 37.5251 8.8019C35.5504 12.4232 33.5744 15.4926 31.5997 18.2006Z"
          fill="currentColor"
        />
      </svg>
    </div>
    <div class="indicator__inner-text">
      <div class="card-percent">
        72<span class="special-number">.7</span><sup class="special">%</sup>
      </div>
      <div class="card-header">Лояльность</div>
      <div class="card-meaning">ниже среднего</div>
      <div class="card-description">
        по отрасли: FMCG <br />
        значений слева от медианы 52.0% - 83.1%
      </div>
      <div class="card-grade">
        <svg
          width="16"
          height="10"
          viewBox="0 0 16 10"
          fill="#70a74b"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M7.27299 1.26978L1.09292 7.81338C0.490617 8.45111 0.942737 9.5 1.81993 9.5H14.1801C15.0573 9.5 15.5094 8.45111 14.9071 7.81338L8.72701 1.26978C8.33239 0.851943 7.66761 0.851943 7.27299 1.26978Z"
            stroke="#70a74b"
          />
        </svg>

        <span>3.1</span>
      </div>
    </div>
    <svg width="283px" height="293px" viewBox="0 0 42 42" class="base">
      <!-- график -->
      <circle
        class="base-ring"
        cx="21"
        cy="21"
        r="15"
        fill="transparent"
        stroke="white"
        stroke-width="2"
      ></circle>

      <!-- внутренний круг -->
      <circle
        class="base-ring"
        cx="21"
        cy="21"
        r="15"
        fill="#fff"
        stroke="transparent"
        stroke-width="1"
      ></circle>

      <circle
        class="grey-segment"
        cx="21"
        cy="21"
        r="15.91549430918954"
        fill="transparent"
        stroke="#ECECEC"
        stroke-width="1.1"
        :stroke-dasharray="calculateValues(34.5)"
        stroke-dashoffset="-35"
        stroke-linecap="round"
      ></circle>

      <circle
        class="green-segment segment"
        cx="21"
        cy="21"
        r="15.91549430918954"
        fill="transparent"
        stroke="#70a74b"
        stroke-width="1.4"
        :stroke-dasharray="calculateValues(value2)"
        stroke-dashoffset="-13"
        stroke-linecap="round"
      ></circle>

      <circle
        class="yellow-segment segment"
        cx="21"
        cy="21"
        r="15.91549430918954"
        fill="transparent"
        stroke="#fbd229"
        stroke-width="1.4"
        :stroke-dasharray="calculateValues(value1)"
        stroke-dashoffset="20"
        stroke-linecap="round"
      ></circle>
      <defs>
        <linearGradient
          id="paint_linear"
          x1="0"
          y1="50%"
          x2="100%"
          y2="50%"
          gradientUnits="userSpaceOnUse"
        >
          <stop stop-color="#3086EC" />
          <stop offset="10" stop-color="#39F7D7" />
        </linearGradient>
      </defs>
    </svg>
  </div>
</template>

<script>
export default {
  name: "IndicatorBase",
  props: {
    value1: {
      type: Number,
      default: 33,
    },
    value2: {
      type: Number,
      default: 29,
    },
    maxValue: {
      type: Number,
      default: 100,
    },
    currency: {
      type: String,
      default: "$",
    },
  },

  computed: {
    reduceFontSize() {
      return this.value > 100000000;
    },
  },
  methods: {
    calculateValues(value) {
      let percentage = Math.round((value * 100) / this.maxValue);
      let residue = 100 - percentage;
      return `${percentage} ${residue}`;
    },
  },
};
</script>

<style lang="scss">
@font-face {
  font-family: "Gotham Pro Regular";
  src: url("../assets/fonts/GothamPro.eot");
  src: url("../assets/fonts/GothamPro.eot?#iefix") format("embedded-opentype"),
    url("../assets/fonts/GothamPro.woff") format("woff"),
    url("../assets/fonts/GothamPro.ttf") format("truetype");
  font-weight: normal;
  font-style: normal;
}
.base {
  margin-top: 5px;
  margin-left: 21px;
}
.indicator-base {
  position: relative;
}
.card-icon {
  position: absolute;
  z-index: 2;
  width: 40px;
  height: 50px;
  color: rgb(204, 204, 204);
  top: 2px;
  right: 125px;
}
.indicator {
  &__inner-text {
    display: flex;
    flex-direction: column;
    align-items: center;
    position: absolute;
    top: 52%;
    left: 50%;
    transform: translateY(-50%) translateX(-50%);
  }

  &__counter {
    width: 100%;
    text-align: center;
    font-style: normal;
    font-weight: bold;
    font-size: 16px;
    line-height: 30px;
    position: relative;

    @media screen and (max-width: 1200px) {
      font-size: 17px;
    }

    &_white,
    &_blue {
      position: absolute;
      width: 100%;
      text-align: center;
      top: 50%;
    }

    &_white {
      color: #fff;
      z-index: 2;
      right: 50%;
      transform: translate(50%, 59%);
      -webkit-transform: translate(50%, 59%);
      -moz-transform: translate(50%, 59%);
      -ms-transform: translate(50%, 59%);
      -o-transform: translate(50%, 59%);
    }
    &_blue {
      color: #0071e9;
      right: 50%;
      z-index: 1;
      transform: translate(53%, 60%);
      -webkit-transform: translate(53%, 60%);
      -moz-transform: translate(53%, 60%);
      -ms-transform: translate(53%, 60%);
      -o-transform: translate(53%, 60%);
    }
  }
  &__text {
    font-style: normal;
    font-size: 12px;
    line-height: 22px;
    color: #000;

    @media screen and (max-width: 1200px) {
      font-weight: 500;
      font-size: 14px;
    }
  }

  &__target {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    color: #0071e9;
    text-align: center;

    span {
      margin-top: 15px;
      font-style: normal;
      font-weight: 300;
      font-size: 16px;
      line-height: 28px;
      color: #000;
    }

    .btn {
      margin-top: 20px;
    }
  }
}
.circle-minor {
  width: 190px;
  height: 190px;
  position: absolute;
  z-index: 1;
  top: 39px;
  right: 40px;

  @media screen and (max-width: 1200px) {
    width: 140px;
    height: 140px;
    position: absolute;
    z-index: 1;
    top: 24px;
    right: 24px;
  }

  &__circle {
    width: 12px;
    height: 12px;
    position: absolute;
    background: linear-gradient(1.22deg, #36cfa1 1.19%, #d3fe5a 99.15%);
    border-radius: 50%;
  }
}
.minify-font-size {
  font-size: 16px;

  @media screen and (max-width: 1200px) {
    font-size: 13px;
  }
}
.minify-font-size + .indicator__text {
  padding-top: 15px;
}
.card-description {
  text-align: center;
  width: 175px;
  color: rgb(185, 185, 185);
  font-size: 11px;
  margin-left: 17px;
  margin-bottom: 9px;
}
.card-percent {
  font-size: 47px;
  font-family: "Gotham Pro Regular";
  margin-top: 1px;
  margin-left: 19px;
  color: rgb(85, 85, 85);
  letter-spacing: 0.1px;
  font-weight: 500;
}
.card-header {
  font-size: 21px;
  font-weight: 700;
  // margin-top: 5px;
  margin-left: 17px;
  margin-bottom: 4px;
  color: rgb(85, 85, 85);
}
.card-meaning {
  margin-left: 15px;
  color: rgb(251, 210, 41);
  font-weight: 700;
  font-size: 16px;
}

.card-grade {
  color: rgb(112, 167, 75);
}
.special-number {
  margin-left: -2px;
  font-size: 24px;
  color: rgb(85, 85, 85);
}
.special {
  font-size: 17px;
  color: rgb(185, 185, 185);
  margin-left: -15px;
  position: absolute;
  top: 5px;
}
</style>
