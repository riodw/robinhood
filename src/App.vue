<template>
  <!-- https://preview.redd.it/9cwrc6k687p81.jpg?width=1242&format=pjpg&auto=webp&s=48b8f7c09ca324a92f0eb1597597f25375beee46 -->
  <!-- https://pbs.twimg.com/media/EuCRmkzXAAIeI8l?format=jpg&name=large -->
  <!-- https://developers.google.com/chart/interactive/docs/gallery/linechart -->
  <div id="app">
    <div class="d-flex justify-content-around align-items-center w-100 vh-100">
      <!-- <div class="d-flex justify-content-around w-100 vh-100"> -->
      <div
        id="robinhood"
        class="card shadow position-relative rounded-0"
        style="min-width: 278px; width: 278px; height: 600px"
      >
        <nav
          class="d-flex justify-content-between ps-4 pe-2 pt-2 mx-2 mb-4"
          style="font-size: 0.8rem"
        >
          <!-- <small> <i class="bi bi-reception-4"></i> Verizon LTE </small> -->
          <div style="font-family: Inter; font-size: 0.7rem; font-weight: 600">
            10:05
          </div>
          <div>
            <i class="bi bi-reception-4 pe-1"></i>
            <i class="bi bi-wifi pe-1"></i>
            <i class="bi bi-battery-full" style="font-size: 0.8rem"></i>
          </div>
        </nav>
        <div
          class="mb-0"
          style="padding: 0.5rem 1rem 0.8rem 1rem; margin-top: 0.42rem"
        >
          <div
            class="d-flex justify-content-between"
            style="font-weight: 600; margin-bottom: 0.85rem"
          >
            <div>
              <h5 style="margin-bottom: 0.18rem">Investing</h5>
              <h5 class="m-0">$535,489.69</h5>
            </div>
            <div>
              <button
                class="btn btn-primary btn-sm green rounded-pill border-0 py-1 mt-1"
                style="
                  background-color: #e4fae5;
                  font-size: 0.57rem;
                  font-weight: 800;
                  padding-left: 0.8rem;
                "
              >
                <i class="bi bi-gift-fill"></i> Rewards
              </button>
            </div>
          </div>
          <div style="font-size: 0.57rem">
            <div class="mb-1">
              <span class="green" style="font-weight: 800">
                <span class="up" style="margin-right: 2px"></span>
                $301,200.00 (128.56%)
              </span>
              Today
            </div>
            <div class="">
              <span class="green" style="font-weight: 800">
                <span class="up" style="margin-right: 2px"></span>
                $0.00000 (0.00%)
              </span>
              After-Hours
            </div>
          </div>
          <div
            class="border-bottom my-3"
            style="
              height: 100px;
              margin-top: -20px;
              margin-left: -16px;
              margin-right: -16px;
            "
          >
            <div style="transform: translateY(-2.2rem)">
              <apexchart
                :options="chartOptions"
                :series="series"
                width="100%"
                height="160px"
              ></apexchart>
            </div>
          </div>
          <div
            class="d-flex justify-content-between mb-1"
            style="padding-top: 0.13rem"
          >
            <button class="btn b-green text-white btn-time py-0">1D</button>
            <button class="btn green btn-time">1W</button>
            <button class="btn green btn-time">1M</button>
            <button class="btn green btn-time">3M</button>
            <button class="btn green btn-time">1Y</button>
            <button class="btn green btn-time">ALL</button>
          </div>
          <div
            class="w-100"
            style="
              height: 0.05rem;
              background-color: #e8e8e8;
              margin: 0.875rem 0 0.8rem 0;
            "
          ></div>
          <div
            class="d-flex justify-content-between"
            style="font-size: 0.58rem"
          >
            <div>Buying Power</div>
            <div>
              $4,579.38
              <i class="bi bi-chevron-right text-opacity-50 text-secondary"></i>
            </div>
          </div>
        </div>
        <div class="bg-gray p-1">
          <div
            class="d-flex bg-white flex-column justify-content-between text-center p-3"
            style="font-size: 0.8rem; height: 140px; border-radius: 0.19rem"
          >
            <div>
              Your're all caught up!
              <br />
              New cards will be added here as they
              <br />
              become available.
            </div>
            <div class="green">Start Over</div>
          </div>
        </div>
        <div
          class="mb-0"
          style="padding: 0.5rem 1rem 0.8rem 1rem; margin-top: 0.25rem"
        >
          <div
            class="d-flex justify-content-between"
            style="font-weight: 600; margin-bottom: 0.85rem"
          >
            <div>
              <h6 style="margin-bottom: 0.18rem">Options</h6>
            </div>
          </div>
        </div>
        <div
          class="d-flex flex-column position-absolute align-items-center bottom-0 bg-white w-100 bg-white"
        >
          <nav
            class="d-flex justify-content-between align-items-center w-100"
            style="padding: 0.54rem 1.5rem; margin-bottom: 0.55rem"
          >
            <div>
              <i class="bi bi-graph-up"></i>
            </div>
            <div class="opacity-50">
              <i class="bi bi-cash-stack"></i>
            </div>
            <div class="opacity-50">
              <i class="bi bi-search"></i>
            </div>
            <div class="opacity-50">
              <i class="bi bi-chat-left-dots-fill"></i>
            </div>
            <div class="opacity-50">
              <i class="bi bi-person-fill"></i>
            </div>
          </nav>
          <div
            class="rounded-pill"
            style="
              width: 100px;
              height: 3.5px;
              background-color: #000;
              margin-bottom: 0.4rem;
            "
          ></div>
        </div>
      </div>
      <!-- <div
        class="card shadow"
        style="min-width: 278px; width: 278px; height: 600px"
      >
        <img src="./assets/IMG.jpg" alt="" />
      </div> -->
      <div class="card shadow">
        <div class="card-header">
          <h4 class="m-0">Settings</h4>
        </div>
        <div class="card-body">asdf</div>
      </div>
    </div>
  </div>
</template>

<script>
import VueApexCharts from "vue3-apexcharts";

export default {
  name: "App",
  components: {
    apexchart: VueApexCharts,
  },
  data() {
    return {
      chartOptions: {
        chart: {
          id: "vuechart-example",
          type: "line",
          parentHeightOffset: 0,
          toolbar: {
            show: false,
          },
        },
        // xaxis: {
        //   categories: [1991, 1992, 1993, 1994, 1995, 1996, 1997, 1998],
        // },
        legend: {
          show: false,
        },
        yaxis: {
          show: false,
        },
        xaxis: {
          labels: {
            show: false,
          },
          axisBorder: {
            show: false,
          },
          axisTicks: {
            show: false,
          },
        },
        grid: {
          show: false,
          padding: {
            top: 0,
            right: 0,
            bottom: 0,
            left: 0,
          },
        },
        stroke: {
          show: true,
          curve: "smooth",
          lineCap: "butt",
          colors: undefined,
          width: 1.3,
          dashArray: 0,
        },
        colors: ["#2ec62d"],
      },
      series: [
        {
          name: "series-1",
          data: [
            // 1, 0.5,
            167391904, 161576838, 161413854, 152177211, 140762210, 144381072,
            // 154352310, 165531790, 175748881, 187064037, 197520685, 210176418,
            196122924, 207337480, 200258882, 186829538, 192456897, 204299711,
            // 192759017, 203596183, 208107346, 196359852, 192570783, 177967768,
            190632803, 203725316, 218226177, 210698669, 217640656, 216142362,
            // 201410971, 196704289, 190436945, 178891686, 171613962, 157579773,
            158677098, 147129977, 151561876, 151627421, 143543872, 136581057,
            // 135560715, 122625263, 112091484, 98810329, 99882912, 94943095,
            104875743, 116383678, 125028841, 123967310, 133167029, 128577263,
            // 115836969, 119264529, 109363374, 113985628, 114650999, 110866108,
            96473454, 104075886, 103568384, 101534883, 115825447, 126133916,
            // 116502109, 130169411, 124296886, 126347399, 131483669, 142811333,
            129675396, 115514483, 117630630, 122340239, 132349091, 125613305,
            // 135592466, 123408762, 111991454, 116123955, 112817214, 113029590,
            108753398, 99383763, 100151737, 94985209, 82913669, 78748268,
            // 63829135, 78694727, 80868994, 93799013, 99042416, 97298692,
            83353499, 71248129, 75253744, 68976648, 71002284, 75052401,
            // 83894030, 90236528, 99739114, 96407136, 108323177, 101578914,
            // 115877608, 112088857, 112071353, 101790062, 115003761, 120457727,
          ].reverse(),
        },
      ],
    };
  },
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@100;500;600;700&display=swap");
@font-face {
  font-family: CapsuleSansText;
  src: url("./assets/CapsuleSansText.ttf");
}
html,
body {
  background-color: #f3f3f5;
}
#app {
  font-family: "CapsuleSansText", "Inter", sans-serif;
  // -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: #f3f3f5;
}
.green {
  color: #00cb00 !important;
}
.b-green {
  background-color: #00c805 !important;
}
.up {
  width: 0px;
  height: 0px;
  border-left: 4px solid transparent;
  border-right: 4px solid transparent;
  border-bottom: 7px solid #00c805;
  // transform: translateY(10px);
  display: inline-block;
  // margin-top: -10px;
}
.btn-time {
  border-radius: 4px !important;
  font-size: 0.57rem !important;
  font-weight: 800;
  padding: 0 0.27rem !important;
}
.bg-gray {
  background-color: #f6f7fd;
}
</style>
