<template>
  <client-only>
    <div class="table-container">
      <table>
        <tr>
          <th class="">
            <div class="d-flex align-items-center">
              <CheckBox class="mt-0" />
              <div>Company<b-icon class="arrow-down"></b-icon></div>
            </div>
          </th>
          <th>License use</th>
          <th>Status</th>
          <th>Users</th>
          <th>About</th>
          <th></th>
          <th></th>
        </tr>
        <tr>
          <td>
            <div class="d-flex align-items-center">
              <CheckBox />
              <div>
                <img src="/customers/Catalog.svg" alt="" class="company-icon" />
              </div>
              <div>
                <p class="m-0 name">Catalog</p>
                <p class="m-0 site">catalogapp.io</p>
              </div>
            </div>
          </td>
          <td><ProgressBar /></td>
          <td>
            <span v-if="customer" class="customer">Customer</span>
            <span v-else class="churned">Churned</span>
          </td>
          <td></td>
          <td></td>
          <td></td>
          <td></td>
        </tr>
      </table>
    </div>
  </client-only>
</template>

<script>
export default {
  name: 'CustomerTable',
  data() {
    return {
        users:[]
    }
  },
}
</script>

<style lang="scss" scoped>
.table-container {
  overflow-x: auto;
}
table {
  border-collapse: collapse;
  table-layout: fixed;
}
td,
th {
  vertical-align: middle;
  white-space: nowrap;
  box-sizing: border-box !important;
}

th {
  height: 44px;
  padding: 0 24px;
  font-family: Inter;
  font-size: 12px;
  font-style: normal;
  font-weight: 500;
  letter-spacing: 0em;
  color: #667085;
}

td {
  height: 72px;
  padding: 0 24px;

  &:nth-child(1) {
    min-width: 370px;
  }

  .company-icon {
    width: 40px;
    height: 40px;
    border-radius: 50%;
  }
}

td .name {
  font-family: Inter;
  font-size: 14px;
  font-style: normal;
  font-weight: 500;
  line-height: 20px;
  letter-spacing: 0em;
  text-align: left;
  color: #101828;
}

.site {
  font-family: Inter;
  font-size: 14px;
  font-style: normal;
  font-weight: 400;
  line-height: 20px;
  letter-spacing: 0em;
  text-align: left;
  color: #667085;
}

.customer {
  font-family: Inter;
  font-size: 12px;
  font-style: normal;
  font-weight: 500;
  line-height: 18px;
  letter-spacing: 0em;
  text-align: center;
  color: #027a48;
  background: #ecfdf3;
  border-radius: 16px;
}

.churned {
  //styleName: Text xs/Medium;
  font-family: Inter;
  font-size: 12px;
  font-style: normal;
  font-weight: 500;
  line-height: 18px;
  letter-spacing: 0em;
  text-align: center;
  color: #344054;
  padding: 2px 8px;
  background: #f2f4f7;
  border-radius: 16px;
}
</style>
