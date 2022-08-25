<template>
  <div>
    <table>
      <!-- Table header -->
      <tr class="table__header-row">
        <th colspan="3" v-for="(col, i) in tabularData.columns" :key="i">
          <span>{{ col.label }}</span
          ><span v-if="col.info" ><i class="light-icon-info-circle"></i></span>
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
            <div class="budget__status__col">
              <div>
                <span
                  ><ProgressBar
                    :progressPercentage="row.budget_status.percentage"
                  />
                </span>
              </div>
              <div>
                <span colspan="3">{{ row.budget_status.cost }}</span>
              </div>
              <div>
                <span colspan="3">{{ row.budget_status.budget }}</span>
              </div>
            </div>
          </td>

          <td colspan="3">
            <div class="budget__status__col">
              <div>
                <span style="font-weight: 600"> {{ row.summary.status }}</span>
              </div>
              <div>
                <span>{{ row.summary.comments }}</span>
              </div>
            </div>
          </td>
          <!-- Actions -->
          <td colspan="3">
            <div class="budget__status__col">
              <div>
                <span><TagComponent :value="row.actions[0]" /></span>
              </div>
              <div>
                <span><TagComponent :value="row.actions[1]" /></span>
              </div>
              <div>
                <span><TagComponent :value="row.actions[2]" /></span>
              </div>
            </div>
          </td>
          <!-- Edit & Delete option -->
          <td colspan="2">
            <div class="actions__col">
              <span><i class="light-icon-pencil"></i></span
              ><span><i class="light-icon-trash"></i></span>
            </div>
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>


<script>
import sampleData from "@/sample-data/sampleData.json";
import TagComponent from "@/components/TagComponent.vue";
import ProgressBar from "@/components/ProgressBar.vue";
export default {
  data() {
    return {
      tabularData: sampleData,
    };
  },
  components: {
    TagComponent,
    ProgressBar,
  },
};
</script>

<style lang='scss'>
table,
tr,
td,
th {
  border: none;
  border-collapse: collapse;
}
table {
  padding: 8px;

  .table__header-row {
    //   display: flex;
    //   align-items: center;
    background-color: #eaeef4;
    th {
      text-align: left;
      padding: 16px;
    }
  }

  .table__body {
    background-color: #fff;
    tr {
      td {
        padding: 12px;
        border-bottom: 1px solid lightgray;
      }
    }
    .budget__status__col {
      display: flex;
      flex-direction: column;
      gap: 16px;
    }
    .actions__col {
      display: flex;
      gap: 12px;
      font-weight: 600;
      span {
        cursor: pointer;
      }
    }
    td {
      text-align: left;
    }
  }
}
</style>