<template>
  <client-only>
    <div class="table-container">
      <table>
        <tr>
          <th>
            <CheckBox class="mt-0" /> company<b-icon
              class="arrow-down"
            ></b-icon>
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
          <td></td>
          <td></td>
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
export default {}
</script>

<style>
.table-container {
  overflow-x: auto;
}
table {
  border-collapse: collapse;
  width: 100%;
}
td,
th {
  vertical-align: middle;
}

th {
  height: 44px;
}

td {
  height: 72px;
}

.company-icon {
  width: 40px;
  height: 40px;
  border-radius: 50%;
}

.name {
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
</style>
