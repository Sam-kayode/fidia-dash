<template>
  <div>
    <Navbar />
    <OverviewNav /><var></var>
    <div class="main-container">
      <div class="welcome-section d-flex justify-content-between">
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
            border="false"
          />
        </div>
      </div>
      <div class="statCards">
        <StatCard />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
    return {
      cards: [{ title: 'Total customers', value: '', percent:'', increase:true }],
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

  .import-btn {
    margin-right: 12px;
  }

  .stat-cards{
     display: grid;
    grid-template-columns: 1fr 1fr 1fr;
    grid-gap: 24px;

  }
}
</style>
