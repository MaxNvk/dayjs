<script lang="ts" setup>
import { useDayjs } from '../src/runtime/composables/dayjs';
const card = false
const icon = false
console.log(useDayjs('2022-01-01').fromNow())
</script>

<template>
  <div>
    <module-icon v-if="icon" />
    <module-card v-else-if="card" />
    <table v-else>
      <thead>
        <tr>
          <th>Name</th>
          <th>Code</th>
          <th>Result</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td>Current time</td>
          <td> dayjs().format('dd, DD MMM YYYY HH:mm:ss')</td>
          <td>{{ useDayjs().format('dd, DD MMM YYYY HH:mm:ss') }}</td>
        </tr>
        <tr>
          <td>Relative Time</td>
          <td> dayjs("2023-01-01").FromNow()</td>
          <td> {{ useDayjs("2023-01-01").fromNow() }} </td>
        </tr>
        <tr>
          <td>UTC Time</td>
          <td>dayjs().utc().format('dd, DD MMM YYYY HH:mm:ss')</td>
          <td> {{ useDayjs().utc().format('dd, DD MMM YYYY HH:mm:ss') }}</td>
        </tr>
        <tr>
          <td>Week Start</td>
          <td>dayjs().startOf('week').format('dddd')</td>
          <td> {{ useDayjs().startOf('week').format('dddd') }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style>
table {
  font-size: 1.2em;
  color: #333;
  margin: 20px auto;
  padding: 30px;
  border: 1px solid #ccc;
}
table tr {
  border: 1px solid #ccc;
}

table td {
  width: 300px;
  padding: 10px;
}

.row > label {
  width: 400px;
  text-align: right;
}

:root {
  --color: #243746;
  --color-primary: #158876;
  --color-secondary: #0e2233;
  --bg: #f3f5f4;
  --bg-secondary: #fff;
  --border-color: #ddd;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  background-color: var(--bg);
  color: var(--color);
  transition: background-color .3s;
}
</style>

