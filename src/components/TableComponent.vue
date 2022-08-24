<template>
  <div>
    <table>
      <!-- Table header -->
      <tr class="table__header-row">
        <th v-for="(col, i) in tabularData.columns" :key="i">
          <span>{{ col.label }}</span
          ><span v-if="col.info"><i class="light-icon-info-circle"></i></span>
        </th>
      </tr>
      <!-- Table body -->
      <tbody class="table__body">
        <tr v-for="(row, j) in tabularData.rows" :key="j">
          <td>{{ row.name }}</td>
          <td>{{ row.description }}</td>
          <td>{{ row.type }}</td>
          <td>{{ row.period }}</td>
          <td>{{ row.start }}</td>
          <td>{{ row.end }}</td>
          <td>{{ row.scope }}</td>
          <!-- Budget Column -->
          <!-- <td v-for="item of row.budget_status">{{item}}</td> -->
          <td>
            <template >
              <tr>
                <td>{{ row.budget_status.percentage }}</td>
              </tr>
              <tr >
                <td>{{ row.budget_status.cost }}</td>
              </tr>
              <tr >
                <td>{{ row.budget_status.budget }}</td>
              </tr>
            </template>
          </td>

          <td>
            <tr>
                <td>{{row.summary.status}}</td>
            </tr>
            <tr>
                <td>{{row.summary.comments}}</td>
            </tr>
          </td>
          <!-- Actions -->
<td>
            <tr>
                <td>{{row.actions[0]}}</td>
            </tr>
            <tr>
                <td>{{row.actions[1]}}</td>
            </tr>
            <tr>
                <td>{{row.actions[2]}}</td>
            </tr>
          </td>
          <!-- Edit & Delete option -->
          <td><span><i class="light-icon-pencil"></i></span><span><i class="light-icon-trash"></i></span></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>


<script>
import sampleData from "@/sample-data/sampleData.json";
export default {
  data() {
    return {
      tabularData: sampleData,
    };
  },
};
</script>

<style lang='scss'>
.table__header-row {
  //   display: flex;
  //   align-items: center;
  th {
    text-align: left;
  }
}

.table__body {
  td {
    text-align: left;
  }
}
</style>