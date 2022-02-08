<template>
  <div>
    <Navbar />
    <OverviewNav /><var></var>
    <div class="main-container">
      <div class="welcome-section d-lg-flex justify-content-between">
        <div class="welcome-container">
          <h1 class="header">Welcome back, Olivia</h1>
          <p class="description-text">
            Track, manage and forecast your customers and orders.
          </p>
        </div>
        <div>
          <Button
            icon="/upload.svg"
            button-content="Import"
            class="import-btn"
          />
          <Button
            icon="/plus.svg"
            button-content="Add"
            background="#7F56D9"
            active-color="#ffffff"
            :border=false
          />
        </div>
      </div>
      <div class="stat-cards">
        <StatCard
          v-for="(card, index) in cards"
          :key="index"
          :title="card.title"
          :value="card.value"
          :percent="card.percent"
          :increase="card.increase"
        />
      </div>
      <div
        class="filter-bar d-flex justify-content-between flex-column flex-lg-row"
      >
        <div class="filters d-flex flex-column d-md-block order-2">
          <div class="filter-btns order-1 order-md-2 d-md-inline">
            <FilterBtn button-content="All time" /><FilterBtn
              button-content="US, AU, +4"
            />
          </div>
          <Button
            icon="/filter.svg"
            button-content="More filters"
            class="edit-btn mr-0"
          />
        </div>
        <div class="search-cont order-1 order-lg-2 order-"><SearchBar /></div>
      </div>
      <CustomerTable />
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      cards: [
        {
          title: 'Total customers',
          value: 2420,
          percent: '40%',
          increase: true,
        },
        { title: 'Members', value: 1210, percent: '10%', increase: false },
        { title: 'Active now', value: 316, percent: '20%', increase: true },
      ],
    }
  },
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@200;300;400;500;600;700&display=swap');
.main-container {
  padding: 48px 112px;

  .header {
    font-family: Inter;
    font-size: 30px;
    font-style: normal;
    font-weight: 500;
    line-height: 38px;
    letter-spacing: 0em;
    text-align: left;
    color: #101828;
    margin-bottom: 4px;
  }

  .description-text {
    font-family: Inter;
    font-size: 16px;
    font-style: normal;
    font-weight: 400;
    line-height: 24px;
    letter-spacing: 0em;
    text-align: left;
    color: #667085;
  }
}

.stat-cards {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
  grid-gap: 24px;
  margin-top: 32px;
}

.filter-bar {
  margin-top: 34px;
}

.search-cont {
  width: 320px;
}

@include tablet {
  .stat-cards {
    display: grid !important;
  }

  .search-cont {
    width: 100% !important;
  }
}

@include mobile {
  .main-container {
    height: 64px;
    padding: 32px 16px;

    .edit-btn {
      margin-top: 12px;
    }

    .filter-btns {
      margin-top: 12px;
    }
  }
}
</style>
