<template>
  <!-- https://preview.redd.it/9cwrc6k687p81.jpg?width=1242&format=pjpg&auto=webp&s=48b8f7c09ca324a92f0eb1597597f25375beee46 -->
  <!-- https://pbs.twimg.com/media/EuCRmkzXAAIeI8l?format=jpg&name=large -->
  <!-- https://developers.google.com/chart/interactive/docs/gallery/linechart -->
  <!-- https://apexcharts.com/docs/chart-types/line-chart/ -->
  <div id="app">
    <!-- <div class="d-flex justify-content-around align-items-center w-100 vh-100"> -->
    <div class="d-flex justify-content-center w-100 my-4">
      <div class="position-relative">
        <div class="btn-group w-100 mb-4">
          <button
            @click="phone = 'blank'"
            :class="{ active: phone === 'blank' }"
            class="btn btn-primary"
          >
            Blank
          </button>
          <button
            @click="phone = 'iPhone'"
            :class="{ active: phone === 'iPhone' }"
            class="btn btn-primary"
          >
            iPhone
          </button>
          <button
            @click="phone = 'android'"
            :class="{ active: phone === 'android' }"
            class="btn btn-primary"
          >
            iPoor
          </button>
        </div>
        <div
          class="card shadow position-relative rounded-0 mb-4"
          style="min-width: 278px; width: 278px; height: 600px"
        >
          <div id="robinhood" class="overflow-hidden">
            <nav
              class="d-flex justify-content-between ps-4 pe-2 pt-2 mx-2"
              style="font-size: 0.8rem; margin-bottom: 1.94rem"
            >
              <!-- <small> <i class="bi bi-reception-4"></i> Verizon LTE </small> -->
              <div
                style="font-family: Inter; font-size: 0.7rem; font-weight: 600"
              >
                {{ twofour ? time : twelvetime }}
              </div>
              <div style="margin-right: 5px">
                <i :class="data" class="bi pe-1"></i>
                <i :class="wifi" class="bi pe-1"></i>
                <i :class="battery" class="bi"></i>
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
                  <h5 class="m-0">
                    ${{
                      Number(end).toLocaleString(undefined, {
                        minimumFractionDigits: 2,
                        maximumFractionDigits: 2,
                      })
                    }}
                  </h5>
                </div>
                <div>
                  <button
                    :class="end - start > 0 ? 'green' : 'red'"
                    :style="
                      end - start > 0
                        ? 'background-color: #e4fae5'
                        : 'background-color: #feede4'
                    "
                    class="d-flex align-items-center btn btn-primary btn-sm rounded-pill border-0 py-1 mt-1"
                    style="font-size: 0.57rem; font-weight: 800"
                  >
                    <svg
                      fill="none"
                      height="10"
                      role="img"
                      viewBox="0 0 24 24"
                      width="13"
                      xmlns="http://www.w3.org/2000/svg"
                    >
                      <path
                        clip-rule="evenodd"
                        d="M9.02503 2.95626C8.38753 2.425 7.64377 2 6.68752 2C4.88126 2 3.5 3.38126 3.5 5.18752C3.5 6.99378 4.88126 8.37504 6.68752 8.37504H17.3126C19.1189 8.37504 20.5001 6.99378 20.5001 5.18752C20.5001 3.38126 19.1189 2 17.3126 2C16.3563 2 15.6126 2.425 14.9751 2.95626L12.0001 6.40458L9.02503 2.95626ZM7.628 4.39866C7.23596 4.09394 6.96119 4 6.68752 4C5.98583 4 5.5 4.48583 5.5 5.18752C5.5 5.88921 5.98583 6.37504 6.68752 6.37504H9.33311L7.628 4.39866ZM16.3721 4.39866L14.667 6.37504H17.3126C18.0143 6.37504 18.5001 5.88921 18.5001 5.18752C18.5001 4.48583 18.0143 4 17.3126 4C17.0389 4 16.7641 4.09394 16.3721 4.39866Z"
                        :fill="end - start > 0 ? '#00c805' : '#ff5000'"
                        fill-rule="evenodd"
                      ></path>
                      <path
                        d="M20 22H13V10.5H20V22Z"
                        :fill="end - start > 0 ? '#00c805' : '#ff5000'"
                      ></path>
                      <path
                        d="M4 10.5H11V22H4V10.5Z"
                        :fill="end - start > 0 ? '#00c805' : '#ff5000'"
                      ></path>
                    </svg>
                    Rewards
                  </button>
                </div>
              </div>
              <div style="font-size: 0.57rem">
                <div class="mb-1">
                  <span
                    :class="end - start > 0 ? 'green' : 'red'"
                    style="font-weight: 800"
                  >
                    <span
                      :class="end - start > 0 ? 'up' : 'down'"
                      style="margin-right: 2px"
                    ></span>
                    ${{ dayGain }} ({{ percentChangeDay }}%)
                  </span>
                  Today
                </div>
                <div style="height: 13.68px">
                  <div v-if="!inHours()">
                    <span
                      :class="after_hours > 0 ? 'green' : 'red'"
                      style="font-weight: 800"
                    >
                      <span
                        :class="after_hours > 0 ? 'up' : 'down'"
                        style="margin-right: 2px"
                      ></span>
                      ${{
                        Number(after_hours).toLocaleString(undefined, {
                          minimumFractionDigits: 2,
                          maximumFractionDigits: 2,
                        })
                      }}
                      ({{ percentChangeAfter }}%)
                    </span>
                    After-Hours
                  </div>
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
                :class="end - start > 0 ? 'green' : 'red'"
                class="d-flex justify-content-between mb-1"
                style="padding-top: 0.13rem"
              >
                <button
                  :class="{ 'b-active': time_range === '1D' }"
                  class="btn btn-time"
                >
                  1D
                </button>
                <button
                  :class="{ 'b-active': time_range === '1W' }"
                  class="btn btn-time"
                >
                  1W
                </button>
                <button
                  :class="{ 'b-active': time_range === '1M' }"
                  class="btn btn-time"
                >
                  1M
                </button>
                <button
                  :class="{ 'b-active': time_range === '3M' }"
                  class="btn btn-time"
                >
                  3M
                </button>
                <button
                  :class="{ 'b-active': time_range === '1Y' }"
                  class="btn btn-time"
                >
                  1Y
                </button>
                <button
                  :class="{ 'b-active': time_range === 'ALL' }"
                  class="btn btn-time"
                >
                  ALL
                </button>
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
                  ${{ Number(buying_power.toFixed(2)).toLocaleString() }}
                  <i
                    class="bi bi-chevron-right text-opacity-50 text-secondary"
                  ></i>
                </div>
              </div>
            </div>
            <div class="bg-gray p-1">
              <div
                v-if="!error"
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
                <div :class="end - start > 0 ? 'green' : 'red'">Start Over</div>
              </div>
              <div v-else class="text-center" style="heig">
                There was an error loading your <br />
                notifications.
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
              <!-- v-if="phone === 'iPhone'" -->
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
          <img
            id="iphone"
            v-show="phone === 'iPhone'"
            src="./assets/iphone.png"
            alt=""
          />
          <img
            id="android"
            v-show="phone === 'android'"
            src="./assets/android.png"
            alt=""
          />
        </div>
        <div class="text-center w-100">
          <button class="btn btn-primary">
            <i class="bi bi-arrow-down"></i>
            Download
          </button>
        </div>
      </div>
      <!-- <div
        class="card shadow"
        style="min-width: 278px; width: 278px; height: 600px; margin-left: 5rem"
      >
        <img src="./assets/red.jpg" />
      </div> -->
      <div class="card shadow" style="width: 400px; margin-left: 5rem">
        <div class="card-header">
          <h4 class="m-0">Settings</h4>
        </div>
        <div class="card-body">
          <div class="row">
            <div class="col mb-3">
              <div class="row">
                <div class="col">
                  <label>Time</label>
                </div>
                <div class="col form-check form-switch">
                  <small>
                    <label class="form-check-label">
                      <i> 24 hr </i>
                      <input
                        v-model="twofour"
                        class="form-check-input"
                        type="checkbox"
                        checked
                      />
                    </label>
                  </small>
                </div>
              </div>
              <input v-model="time" class="form-control" type="time" />
            </div>
            <div class="col mb-3">
              <label>Stat Bar</label>
              <div class="btn-group btn-group">
                <div class="btn-group" role="group">
                  <button
                    class="btn btn-outline-primary dropdown-toggle"
                    data-bs-toggle="dropdown"
                  >
                    <i :class="data" class="bi pe-1"></i>
                  </button>
                  <ul class="dropdown-menu">
                    <li>
                      <button
                        @click="data = 'bi-reception-4'"
                        class="dropdown-item"
                      >
                        <i class="bi bi-reception-4"></i>
                      </button>
                      <button
                        @click="data = 'bi-reception-3'"
                        class="dropdown-item"
                      >
                        <i class="bi bi-reception-3"></i>
                      </button>
                      <button
                        @click="data = 'bi-reception-2'"
                        class="dropdown-item"
                      >
                        <i class="bi bi-reception-2"></i>
                      </button>
                      <button
                        @click="data = 'bi-reception-1'"
                        class="dropdown-item"
                      >
                        <i class="bi bi-reception-1"></i>
                      </button>
                    </li>
                  </ul>
                </div>
                <div class="btn-group" role="group">
                  <button
                    class="btn btn-outline-primary dropdown-toggle"
                    data-bs-toggle="dropdown"
                  >
                    <i :class="wifi" class="bi pe-1"></i>
                  </button>
                  <ul class="dropdown-menu">
                    <li>
                      <button @click="wifi = 'bi-wifi'" class="dropdown-item">
                        <i class="bi bi-wifi"></i>
                      </button>
                      <button @click="wifi = 'bi-wifi-2'" class="dropdown-item">
                        <i class="bi bi-wifi-2"></i>
                      </button>
                      <button @click="wifi = 'bi-wifi-1'" class="dropdown-item">
                        <i class="bi bi-wifi-1"></i>
                      </button>
                    </li>
                  </ul>
                </div>
                <div class="btn-group" role="group">
                  <button
                    class="btn btn-outline-primary dropdown-toggle"
                    data-bs-toggle="dropdown"
                  >
                    <i :class="battery" class="bi"></i>
                  </button>
                  <ul class="dropdown-menu">
                    <li>
                      <button
                        @click="battery = 'bi-battery-full'"
                        class="dropdown-item"
                      >
                        <i class="bi bi-battery-full"></i>
                      </button>
                      <button
                        @click="battery = 'bi-battery-half'"
                        class="dropdown-item"
                      >
                        <i class="bi bi-battery-half"></i>
                      </button>
                      <button
                        @click="battery = 'bi-battery'"
                        class="dropdown-item"
                      >
                        <i class="bi bi-battery"></i>
                      </button>
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
          <div class="row">
            <div class="col mb-3">
              <label>Start</label>
              <input
                v-model="start"
                @input="update()"
                min="1"
                class="form-control"
                type="number"
              />
            </div>
            <div class="col mb-3">
              <label>End</label>
              <input
                v-model="end"
                @input="update()"
                min="0"
                class="form-control"
                type="number"
              />
            </div>
          </div>
          <div class="mb-3">
            <label>After Hours</label>
            <input
              v-model="after_hours"
              @input="update()"
              :disabled="inHours()"
              class="form-control"
              type="number"
            />
          </div>
          <div class="mb-1">
            <label>Volatility ({{ volatility }})</label>
            <input
              v-model="volatility"
              @change="chart()"
              class="form-range"
              type="range"
            />
          </div>
          <div>
            <label>Time Range</label>
            <div class="btn-group w-100 mb-3">
              <button
                @click="time_range = '1D'"
                :class="
                  time_range === '1D' ? 'btn-primary' : 'btn-outline-primary'
                "
                class="btn"
              >
                1D
              </button>
              <button
                @click="time_range = '1W'"
                :class="
                  time_range === '1W' ? 'btn-primary' : 'btn-outline-primary'
                "
                class="btn"
              >
                1W
              </button>
              <button
                @click="time_range = '1M'"
                :class="
                  time_range === '1M' ? 'btn-primary' : 'btn-outline-primary'
                "
                class="btn"
              >
                1M
              </button>
              <button
                @click="time_range = '3M'"
                :class="
                  time_range === '3M' ? 'btn-primary' : 'btn-outline-primary'
                "
                class="btn"
              >
                3M
              </button>
              <button
                @click="time_range = '1Y'"
                :class="
                  time_range === '1Y' ? 'btn-primary' : 'btn-outline-primary'
                "
                class="btn"
              >
                1Y
              </button>
              <button
                @click="time_range = 'ALL'"
                :class="
                  time_range === 'ALL' ? 'btn-primary' : 'btn-outline-primary'
                "
                class="btn"
              >
                ALL
              </button>
            </div>
          </div>
          <div class="mb-3">
            <label>Buying Power</label>
            <input v-model="buying_power" class="form-control" type="number" />
          </div>
          <div class="form-check">
            <label class="form-check-label">
              Error
              <input v-model="error" class="form-check-input" type="checkbox" />
            </label>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import moment from "moment";
import VueApexCharts from "vue3-apexcharts";

export default {
  name: "App",
  components: {
    apexchart: VueApexCharts,
  },
  data() {
    return {
      // SETTINGS
      time: moment(Date.now()).format("HH:mm"),
      // time: "13:20",
      twofour: false,
      data: "bi-reception-4", // bi-reception-1, bi-reception-2, bi-reception-3
      wifi: "bi-wifi", // bi-wifi-1, bi-wifi-2
      battery: "bi-battery-full", // bi-battery-half
      start: 100,
      // start: 234289,
      end: 200,
      // end: 535489.68,
      time_range: "1D",
      volatility: 20,
      buying_power: 4579.38,
      after_hours: 10,
      error: false,
      phone: "blank",

      // CHART
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
  methods: {
    inHours() {
      return (
        moment(this.time, "HH:mm").isSameOrAfter(moment("09:30", "HH:mm")) &&
        moment(this.time, "HH:mm").isSameOrBefore(moment("16:00", "HH:mm"))
      );
    },
    update() {
      this.chartOptions = {
        ...this.chartOptions,
        ...{
          colors: this.end - this.start > 0 ? ["#2ec62d"] : ["#fe5100"],
        },
      };
      this.chart();
    },
    chart() {
      var data = [];

      var n = 0;
      var e = 0;

      if (this.inHours()) {
        n = this.end - this.start;
        e = 61;
      } else {
        n = this.end - this.start - this.after_hours;
        e = 51;
      }

      n = (n / e).toFixed(2);

      // console.log(n);

      for (let i = 0; i < e; i++) {
        let a = Number((this.start + n * i).toFixed(2));

        let x = Math.floor(
          Math.random() * (this.volatility - this.volatility * -1) +
            this.volatility * -1
        );
        x = Number((x * 0.01).toFixed(2));
        x = a * x;

        console.log(x, a);
        data.push(Math.trunc(a + x));
      }

      n = this.start + n * e;

      if (!this.inHours())
        for (let i = 0; i < 10; i++) {
          let x = Math.floor(
            Math.random() * (this.volatility - this.volatility * -1) +
              this.volatility * -1
          );

          data.push(Math.trunc(n + (this.after_hours / 10) * i) + x);
        }

      this.series = [
        {
          name: "series-1",
          data: data,
        },
      ];

      console.log(this.volatility);
    },
  },
  computed: {
    twelvetime() {
      return moment(this.time, "HH:mm").format("h:mm");
    },
    dayGain() {
      var n = 0;
      if (this.inHours()) n = this.end - this.start;
      n = this.end - this.after_hours - this.start;
      return Number(n).toLocaleString(undefined, {
        minimumFractionDigits: 2,
        maximumFractionDigits: 2,
      });
    },
    percentChangeDay() {
      var n = 0;
      if (this.inHours()) n = this.end;
      n = this.end - this.after_hours;

      n = ((n - this.start) / Math.abs(this.start)) * 100;

      return Number(n).toLocaleString(undefined, {
        minimumFractionDigits: 2,
        maximumFractionDigits: 2,
      });
    },
    percentChangeAfter() {
      var n = this.end - this.after_hours;
      n = ((this.end - n) / Math.abs(n)) * 100;

      return Number(n).toLocaleString(undefined, {
        minimumFractionDigits: 2,
        maximumFractionDigits: 2,
      });
    },
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
  // background-color: #f3f3f5;
  background-color: #333;
  font-family: Helvetica;
}
#app {
  background-color: #333;
}
#robinhood {
  font-family: "CapsuleSansText", "Inter", sans-serif;
}
#iphone {
  z-index: 1000;
  position: absolute;
  width: 313px;
  top: -17px;
  left: -18px;
  // opacity: 0.4;
}
#android {
  z-index: 1000;
  position: absolute;
  width: 308px;
  height: 624px;
  top: -11px;
  left: -13px;
  // opacity: 0.4;
}
.green,
.green > .btn {
  color: #00cb00 !important;
}
.red,
.red > .btn {
  color: #ff4f00 !important;
}
.green > .b-active {
  color: #fff !important;
  background-color: #00c805 !important;
}
.red > .b-active {
  color: #fff !important;
  background-color: #ff4f00 !important;
}
.up {
  width: 0px;
  height: 0px;
  border-left: 4px solid transparent;
  border-right: 4px solid transparent;
  border-bottom: 7px solid #00c805;
  display: inline-block;
}
.down {
  width: 0px;
  height: 0px;
  border-left: 4px solid transparent;
  border-right: 4px solid transparent;
  border-top: 7px solid #ff4f00;
  display: inline-block;
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
