<template>
  <div class="card-container">
    <div class="d-flex justify-content-between">
      <p class="card-description">{{ title }}</p>
      <b-icon icon="three-dots-vertical"> </b-icon>
    </div>

    <div class="stats d-flex justify-content-between align-items-end">
      <div>
        <h1 class="value">{{ value }}</h1>
        <b-icon v-if="!increase" icon="arrow-down-short" class="red"></b-icon>
        <b-icon v-if="increase" icon="arrow-up-short" class="green"></b-icon>
        <span class="percent" :class="{ decrease: !increase }"
          >{{ percent }}
        </span>
        <span class="last">vs last month</span>
      </div>
      <div class="p-1">
        <img v-if="!increase" class="graph" src="/redLine.svg" alt="" />
        <img v-if="increase" class="graph" src="/greenLine.svg" alt="" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'StatCard',
  props: {
    increase: {
      type: Boolean,
      default: true,
    },
    percent: {
      type: String,
      default: '',
    },
    title: {
      type: String,
      default: '',
    },
    value: {
      type: Number,
      default: null,
    },
  },
}
</script>

<style scoped lang="scss">
.card-container {
  padding: 24px;
  height: 176px;
  border: 1px solid #eaecf0;
  box-shadow: 0px 1px 3px rgba(16, 24, 40, 0.1),
    0px 1px 2px rgba(16, 24, 40, 0.06);
  border-radius: 8px;

  .card-description {
    font-family: Inter, 'sans-serif';
    font-size: 16px;
    font-style: normal;
    font-weight: 500;
    line-height: 24px;
    letter-spacing: 0em;
    text-align: left;
    margin-bottom: 24px;
    color: #101828;
  }
  svg {
    color: #98a2b3;
  }

  .stats {
    .value {
      font-family: Inter, sans-serif;
      font-size: 36px;
      font-style: normal;
      font-weight: 600;
      line-height: 44px;
      letter-spacing: -0.02em;
      text-align: left;
      color: #101828;
      margin-bottom: 16px;
    }
    svg {
      transform: scale(1.7);
      margin-right: 8px;
    }

    .red {
      color: #f04438;
    }

    .green {
      color: #12b76a;
    }
    .graph {
      width: 128px !important;
    }

    .last {
      font-family: Inter, 'sans-serif';
      font-size: 14px;
      font-style: normal;
      font-weight: 500;
      line-height: 20px;
      letter-spacing: 0em;
      text-align: left;
      color: #667085;
    }

    .percent {
      font-family: Inter, 'sans-serif';
      font-size: 14px;
      font-style: normal;
      font-weight: 500;
      line-height: 20px;
      letter-spacing: 0em;
      text-align: center;
      color: #027a48;
      margin-right: 8px;
    }

    .decrease {
      color: #b42318;
    }
  }
}

@include mobile {
  .stats {
    .graph {
      max-width: 96px !important;
    }

    .value {
      font-size: 30px !important;
      line-height: 38px;
    }
  }
}
</style>
