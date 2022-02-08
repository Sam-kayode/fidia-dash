<template>
  <client-only>
    <div class="table-container">
      <table>
        <tr class="divider">
          <th class="">
            <div class="d-flex align-items-center">
              <CheckBox class="mt-0" indeterminate=true />
              <div>Company <img src="/arrow-down.svg" alt="" /></div>
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
      <div class="border d-sm-none"></div>

      <div class="d-flex justify-content-between align-items-center table-base">
        <b-icon icon="arrow-left" class="d-sm-none"></b-icon>
        <div class="nav-btns d-md-flex align-items-center">
          <Button button-content="Previous" class="previous" />
          <Button button-content="Next" />
        </div>
        <div class="p-0 m-0 page">Page <span>1</span> 1 of <span>10</span></div>
        <b-icon icon="arrow-right" class="d-sm-none"></b-icon>
      </div>
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
          progress: 25,
          customer: false,
          users: ['jake', 'jema', 'ade', 'leia', 'tumi', 'kate'],
          about: 'Web app integrations',
          desc: 'Connect web apps seamlessly',
        },
        {
          name: 'Quotient',
          site: 'quotient.co',
          progress: 20,
          customer: true,
          users: [
            'eve',
            'jake',
            'ade',
            'jema',
            'tom',
            'kate',
            'mary',
            'emma',
            'tumi',
            'leia',
            'joe',
          ],
          about: 'Sales CRM',
          desc: 'Web-based sales doc management',
        },
        {
          name: 'Sisyphus',
          site: 'sisyphus.com',
          progress: 50,
          customer: true,
          users: [
            'kate',
            'tom',
            'mary',
            'ade',
            'sophie',
            'emma',
            'tumi',
            'leia',
            'joe',
          ],
          about: 'Automation and workflow',
          desc: 'Time tracking, invoicing and expenses',
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
  margin-top: 25px;
  &::-webkit-scrollbar {
    height: 0.3em;
    cursor: pointer;
  }

  &::-webkit-scrollbar-track {
    -webkit-box-shadow: inset 0 0 6px rgba(31, 26, 26, 0.1);
    box-shadow: inset 0 0 6px rgba(0, 0, 0, 0.1);
    cursor: pointer;
  }

  &::-webkit-scrollbar-thumb {
    border-radius: 10px;
    background: grey;
    width: 40px !important;
    cursor: pointer;
  }
}

table {
  border-collapse: collapse;
  min-width: 100%;
  box-sizing: border-box;
}
.previous {
  margin-right: 12px;
}
th {
  height: 44px;
  padding: 0 24px;
  font-family: Inter, 'sans-serif';
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

.table-base {
  height: 65px;
  border-top: 1px solid #eaecf0;
  padding: 0px 24px;
  width: inherit;

  .nav-btns {
    height: 100%;
  }

  .page {
    //styleName: Text sm/Medium;
    font-family: Inter, 'sans-serif';
    font-size: 14px;
    font-weight: 400;
    font-style: normal;
    line-height: 20px;
    letter-spacing: 0em;
    text-align: left;

    span {
      font-weight: 500;
    }
  }

  svg {
    cursor: pointer;
  }
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
  .nav-btns {
    display: none;
  }
  .border {
    position: relative;
    height: 1px;
    top: 30px;
    right: 0;
    background: #eaecf0;
    width: calc(100vw - 48px);
    margin: 0 auto;
  }
  .table-base {
    height: 117px !important;
  }
}
</style>
