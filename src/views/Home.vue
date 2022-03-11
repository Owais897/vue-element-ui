<template>
  <div class="home">
    <el-table
      ref="multipleTable"
      :data="result.objectData.content"
      element-loading-text="Loading"
      fit
      border
      highlight-current-row
    >
      <el-table-column
        v-for="column in prepareColumn()"
        :key="column.prop"
        :label="column.label"
        :prop="column.prop"
        :width="column.width"
      />
    </el-table>
    {{ getCurrentDate() }}
  </div>
</template>

<script>
import moment from "moment";
export default {
  name: "Home",
  data() {
    return {
      tableColumns: [
        { label: "owais", key: 1, width: 50, prop: "totalHrsWorked" },
      ],
      result: {
        objectData: {
          content: [
            {
              id: 1,
              fromDate: "2021-11-05",
              toDate: "2021-11-11",
              totalHrsWorked: 9.0,
              totalHrsInOffce: 1.0,
              totalHrsRemain: 1.0,
              hrsWorkedOnSaturaday: 1.0,
              hrsWorkedOnSunday: 1.0,
              totalPto: 2.0,
              totalIncompleteDays: 3,
              totalWeekdayWorked: 1,
              totalWeekendWorked: 1,
              totalAbsentDays: 0,
              statsHrsWorkedMin: 1.0,
              statsHrsWorkedMax: 1.0,
              statsHrsWorkedMean: 1.0,
              statsHrsWorkedSD: 1.0,
              statsHrsInOfficeMin: 1.0,
              statsHrsInOfficeMax: 1.0,
              statsHrsInOfficeMean: 1.0,
              statsHrsInOfficeSD: 1.0,
              weekOfYear: 12,
            },
            {
              id: 2,
              fromDate: "2021-11-12",
              toDate: "2021-11-18",
              totalHrsWorked: 13.0,
              totalHrsInOffce: 3.0,
              totalHrsRemain: 3.0,
              hrsWorkedOnSaturaday: 1.0,
              hrsWorkedOnSunday: 1.0,
              totalPto: 3.0,
              totalIncompleteDays: 3,
              totalWeekdayWorked: 3,
              totalWeekendWorked: 3,
              totalAbsentDays: 0,
              statsHrsWorkedMin: 3.0,
              statsHrsWorkedMax: 2.0,
              statsHrsWorkedMean: 3.0,
              statsHrsWorkedSD: 3.0,
              statsHrsInOfficeMin: 2.0,
              statsHrsInOfficeMax: 1.0,
              statsHrsInOfficeMean: 2.0,
              statsHrsInOfficeSD: 2.0,
              weekOfYear: 3,
            },
          ],
          pageable: {
            sort: {
              sorted: true,
              unsorted: false,
              empty: false,
            },
            offset: 0,
            pageNumber: 0,
            pageSize: 10,
            paged: true,
            unpaged: false,
          },
          last: true,
          totalPages: 1,
          totalElements: 2,
          size: 10,
          number: 0,
          sort: {
            sorted: true,
            unsorted: false,
            empty: false,
          },
          numberOfElements: 2,
          first: true,
          empty: false,
        },
        description: "Weekly Attendance Report Fetched Successfully",
      },
    };
  },
  methods: {
    prepareColumn() {
      let col = Object.keys(this.result.objectData.content[0]);
      return [
        ...col.map((v, i) => {
          console.log("i: ", i);
          console.log("v: ", v);
          return {
            label: v,
            key: i,
            width: 150,
            prop: v,
          };
        }),
      ];
    },
    getCurrentDate() {
      let startOfWeek = moment().startOf("week").format("yyyy-MM-DD");
      console.log("startOfWeek: ", startOfWeek);

      let endOfWeek = moment().endOf("week").format("yyyy-MM-DD");
      console.log("endOfWeek: ", endOfWeek);
    },
  },
};
</script>

<style scoped>
.banner {
  background: url("../assets/banner.jpg") no-repeat center;
  height: 500px;
  width: 100%;
  background-size: cover;
  margin-top: -35px;
}
.wrapper {
  margin: 142px 40px;
}
</style>
