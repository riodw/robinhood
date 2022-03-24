<template>
  <!-- https://preview.redd.it/9cwrc6k687p81.jpg?width=1242&format=pjpg&auto=webp&s=48b8f7c09ca324a92f0eb1597597f25375beee46 -->
  <!-- https://pbs.twimg.com/media/EuCRmkzXAAIeI8l?format=jpg&name=large -->
  <div id="app" class="">
    Robinhood
    <div class="d-flex justify-content-around">
      <div
        id="robinhood"
        class="card shadow"
        style="width: 277px; height: 600px"
      >
        <nav
          class="d-flex justify-content-between px-4 pt-1"
          style="font-size: 0.8rem"
        >
          <!-- <small> <i class="bi bi-reception-4"></i> Verizon LTE </small> -->
          <div>4:05</div>
          <div>
            <i class="bi bi-reception-4 pe-1"></i>
            <i class="bi bi-wifi pe-1"></i>
            <i class="bi bi-battery-full"></i>
          </div>
        </nav>
        <div class="card-body mt-1 pb-0">
          <div class="d-flex justify-content-between mb-4">
            <div>
              <h4 class="mb-1">Investing</h4>
              <h4>$535,489.69</h4>
            </div>
            <div>
              <button
                class="btn btn-primary btn-sm rounded-pill border-0 px-2 py-1"
                style="color: #45cb0b; background-color: #e6f9e5"
              >
                <small>
                  <strong> <i class="bi bi-gift-fill"></i> Rewards </strong>
                </small>
              </button>
            </div>
          </div>
          <div class="" style="font-size: 0.7rem">
            <span class="fw-bold green">
              <i class="bi bi-caret-up-fill" style="font-size: 0.8rem"></i>
              $301,200.00 (128.56%)
            </span>
            Today
          </div>
          <div class="" style="font-size: 0.7rem">
            <span class="fw-bold green">
              <i class="bi bi-caret-up-fill" style="font-size: 0.8rem"></i>
              $0.00000 (0.00%)
            </span>
            After-Hours
          </div>
          <div
            class="border-bottom my-3"
            style="height: 71px; margin-left: -16px; margin-right: -16px"
          >
            GRAPH
          </div>
          <div class="d-flex justify-content-between mb-1">
            <div>
              <button
                class="btn b-green text-white btn-sm py-0"
                style="border-radius: 6px"
              >
                <small> 1D </small>
              </button>
            </div>
            <div>
              <button class="btn green btn-sm py-0" style="border-radius: 6px">
                <small>
                  <strong> 1W </strong>
                </small>
              </button>
            </div>
            <div>
              <button class="btn green btn-sm py-0" style="border-radius: 6px">
                <small>
                  <strong> 1M </strong>
                </small>
              </button>
            </div>
            <div>
              <button class="btn green btn-sm py-0" style="border-radius: 6px">
                <small>
                  <strong> 3M </strong>
                </small>
              </button>
            </div>
            <div>
              <button class="btn green btn-sm py-0" style="border-radius: 6px">
                <small>
                  <strong> 1Y </strong>
                </small>
              </button>
            </div>
            <div>
              <button class="btn green btn-sm py-0" style="border-radius: 6px">
                <small>
                  <strong> ALL </strong>
                </small>
              </button>
            </div>
          </div>
          <hr class="bg-secondary" />
          <div class="d-flex justify-content-between" style="font-size: 0.9rem">
            <div>Buying Power</div>
            <div>
              $4,579.38
              <i class="bi bi-chevron-right text-opacity-50 text-secondary"></i>
            </div>
          </div>
        </div>
        <div class="card-body bg-light p-1">
          <div
            class="d-flex bg-white flex-column justify-content-between text-center p-3"
            style="font-size: 0.8rem; height: 140px"
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
        <nav class="d-flex justify-content-between bg-white px-4 py-2">
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
      </div>
      <div class="card">asdf</div>
    </div>
  </div>
</template>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Inter:wght@100;500;600;700&display=swap");
html,
body {
  background-color: #f3f3f5;
}
#app {
  font-family: "Inter", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: #f3f3f5;
}
.green {
  color: #44c70b !important;
}
.b-green {
  background-color: #44c70b !important;
}
</style>
