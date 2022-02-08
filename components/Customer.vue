<template>
  <tr>
    <td>
      <div class="d-flex align-items-center">
        <CheckBox />
        <div>
          <img :src='"/customers/" + name + ".svg"' alt="" class="company-icon" />
        </div>
        <div>
          <p class="m-0 name">{{ name }}</p>
          <p class="m-0 site">{{ site }}</p>
        </div>
      </div>
    </td>
    <td><ProgressBar :width="width"/></td>
    <td>
      <span v-if="customer" class="customer">Customer</span>
      <span v-else class="churned">Churned</span>
    </td>
    <td>
      <Users :users="users" />
    </td>
    <td>
      <p class="about m-0">{{ about }}</p>
      <p class="about-desc m-0">{{ desc }}</p>
    </td>
    <td>
      <div class="icons">
        <img class="bin" src="/bin.svg" alt="" />
        <img class="pen" src="/pen.svg" alt="" />
      </div>
    </td>
  </tr>
</template>

<script>
export default {
  name: 'Customer',
  props: {
    name: {
      type: String,
      default: '',
    },
    site: {
      type: String,
      default: '',
    },
    customer: {
      type: Boolean,
      default: true,
    },
    about: {
      type: String,
      default: '',
    },
     width: {
      type: Number,
      default: null,
    },
    desc: {
      type: String,
      default: '',
    },  
    users: {
      type: Array,
      default: null,
    },
  },
  data() {
    return {}
  },
}
</script>

<style lang="scss" scoped>
td,
th {
  vertical-align: middle;
  white-space: nowrap;
  box-sizing: border-box;

  &:nth-child(last) {
    padding: 28px;
  }
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

.name {
  font-family: Inter, 'sans-serif';
  font-size: 14px;
  font-style: normal;
  font-weight: 500;
  line-height: 20px;
  letter-spacing: 0em;
  text-align: left;
  color: #101828;
}

.site {
  font-family: Inter, 'sans-serif';
  font-size: 14px;
  font-style: normal;
  font-weight: 400;
  line-height: 20px;
  letter-spacing: 0em;
  text-align: left;
  color: #667085;
}

.customer {
  font-family: Inter, 'sans-serif';
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

.company-icon{
    margin-right:12px;
}

.churned {
  font-family: Inter, 'sans-serif';
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
.about {
  font-family: Inter, 'sans-serif';
  font-size: 14px;
  font-style: normal;
  font-weight: 400;
  line-height: 20px;
  letter-spacing: 0em;
  text-align: left;
  color: #101828;
}

.about-desc {
  font-family: Inter, 'sans-serif';
  font-size: 14px;
  font-style: normal;
  font-weight: 400;
  line-height: 20px;
  letter-spacing: 0em;
  text-align: left;
  color: #667085;
}

.bin {
  margin-right: 28px;
  cursor: pointer;
}

.pen {
  cursor: pointer;
}

.divider {
  border-bottom: 1px solid #eaecf0;
  width: 100%;
}

@include mobile {
  th,
  td {
    &:nth-child(n + 3) {
      display: none;
    }
    &:nth-child(1) {
      min-width: 0;
    }
  }
}
</style>
