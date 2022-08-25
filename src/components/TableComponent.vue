<template>
  <div>
    <table>
      <!-- Table header -->
      <tr class="table__header-row">
        <th colspan="3" v-for="(col, i) in tabularData.columns" :key="i">
          <span>{{ col.label }}</span
          ><span v-if="col.info"><i class="light-icon-info-circle"></i></span>
        </th>
      </tr>
      <!-- Table body -->
      <tbody class="table__body">
        <tr v-for="(row, j) in tabularData.rows" :key="j">
          <td colspan="3">{{ row.name }}</td>
          <td colspan="3">{{ row.description }}</td>
          <td colspan="3">{{ row.type }}</td>
          <td colspan="3">{{ row.period }}</td>
          <td colspan="3">{{ row.start }}</td>
          <td colspan="3">{{ row.end }}</td>
          <td colspan="3">{{ row.scope }}</td>
          <!-- Budget Column -->
          <!-- <td v-for="item of row.budget_status">{{item}}</td> -->
          <td colspan="3">
            <template >
              <tr>
                <td colspan="3">{{ row.budget_status.percentage }}</td>
              </tr>
              <tr >
                <td colspan="3">{{ row.budget_status.cost }}</td>
              </tr>
              <tr >
                <td colspan="3">{{ row.budget_status.budget }}</td>
              </tr>
            </template>
          </td>

          <td colspan="3">
            <tr>
                <td>{{row.summary.status}}</td>
            </tr>
            <tr>
                <td>{{row.summary.comments}}</td>
            </tr>
          </td>
          <!-- Actions -->
<td colspan="3">
            <tr>
                <td><TagComponent :value="row.actions[0]"/></td>
            </tr>
            <tr>
                <td><TagComponent :value="row.actions[1]"/></td>
            </tr>
            <tr>
                <td><TagComponent :value="row.actions[2]"/></td>
            </tr>
          </td>
          <!-- Edit & Delete option -->
          <td colspan="2"><span><i class="light-icon-pencil"></i></span><span><i class="light-icon-trash"></i></span></td>
        </tr>
      </tbody>
    </table>
  </div>
</template>


<script>
import sampleData from "@/sample-data/sampleData.json";
import TagComponent from "@/components/TagComponent.vue";
export default {
  data() {
    return {
      tabularData: sampleData,
    };
  },
  components:{
    TagComponent
  }
};
</script>

<style lang='scss'>

table, tr, td,th{
border: none;
 border-collapse: collapse;
}
table{
padding: 8px;


.table__header-row {
  //   display: flex;
  //   align-items: center;
  background-color: #EAEEF4;
  th {
    text-align: left;
  }
}

.table__body {
    background-color: #fff;
  td {
    text-align: left;
  }
}
}

</style>