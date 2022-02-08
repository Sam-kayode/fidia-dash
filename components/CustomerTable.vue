<template>
  <client-only>
    <div class="table-container">
      <table>
        <tr class="divider">
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
        </tr>
        <Customer
          v-for="(company, index) in companies"
          :key="index"
          :name="company.name"
          :site="company.site"
          :width="company.progress"
          :customer="company.customer"
          :users="company.users"
          :about="company.about"
          :desc="company.desc"
        />
      </table>
    </div>
  </client-only>
</template>

<script>
export default {
  name: 'CustomerTable',
  data() {
    return {
      companies: [
        {
          name: 'Catalog',
          site: 'catalogapp.io',
          progress: 80,
          customer: true,
          users: [
            'emma',
            'joe',
            'jake',
            'sophie',
            'eve',
            'leia',
            'jema',
            'tom',
            'mary',
            'kate',
          ],
          about: 'Content curating app',
          desc: 'Brings all your news into one place',
        },
        {
          name: 'Circooles',
          site: 'getcirooles.com',
          progress: 70,
          customer: false,
          users: [
            'jema',
            'kate',
            'mary',
            'emma',
            'tumi',
            'leia',
            'joe',
            'jake',
            'sophie',
            'eve',
            'tom',
            'ade',
            'love',
          ],
          about: 'Design software',
          desc: 'Super lightweight design app',
        },
        {
          name: 'Command+R',
          site: 'cmdr.ai',
          progress: 40,
          customer: true,
          users: ['tumi', 'ade', 'tom', 'leia', 'love', 'jema', 'kate'],
          about: 'Data prediction',
          desc: 'AI and machine learning data',
        },
        {
          name: 'Hourglass',
          site: 'hourglass.app',
          progress: 90,
          customer: true,
          users: ['eve', 'joe', 'jema', 'kate', 'ade'],
          about: 'Productivity app',
          desc: 'Time management and productivity',
        },
        {
          name: 'Layers',
          site: 'getlayers.io',
          progress: 20,
          customer: false,
          users: ['jake', 'jema', 'ade', 'leia', 'tumi', 'kate'],
          about: 'Web app integrations',
          desc: 'Connect web apps seamlessly',
        },
      ],
    }
  },
}
</script>

<style lang="scss" scoped>
.table-container {
  overflow-x: auto;
  box-shadow: 0px 4px 8px -2px rgba(16, 24, 40, 0.1),
    0px 2px 4px -2px rgba(16, 24, 40, 0.06);
  border-radius: 8px;
  margin-top: 27px;
}

table {
  border-collapse: collapse;
  min-width: 100%;
  border: 1px solid #eaecf0;
  box-sizing: border-box;
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
  vertical-align: middle;
  white-space: nowrap;
  box-sizing: border-box !important;

  &:nth-child(last) {
    padding: 28px;
  }
}

.divider {
  border-bottom: 1px solid #eaecf0;
  width: 100%;
}

@include mobile {
  th {
    &:nth-child(n + 3) {
      display: none;
    }
    &:nth-child(1) {
      min-width: 0;
    }
  }
}
</style>
