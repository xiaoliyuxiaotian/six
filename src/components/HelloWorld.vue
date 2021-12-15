<template>
  <div class="hello">
    <div class="header">
      <div class="text">
        <label for="text">条件</label>
        <input type="text" name="text" v-model="text" />
      </div>
      <div class="date">
        <label for="date">日期</label>
        <input type="text" name="date" v-model="date" />
      </div>
      <button @click="cha">查询</button>
    </div>
    <div class="table">
      <el-table :data="table" stripe style="width: 100%">
        <el-table-column prop="date" label="日期" width="180">
        </el-table-column>
        <el-table-column prop="name" label="姓名" width="180">
        </el-table-column>
        <el-table-column prop="address" label="地址"> </el-table-column>
      </el-table>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tableData: [
        {
          date: "2016年05月02日",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1518 弄",
        },
        {
          date: "2016年05月04日",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1517 弄",
        },
        {
          date: "2016年05月01日",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1519 弄",
        },
        {
          date: "2016年05月03日",
          name: "王小虎",
          address: "上海市普陀区金沙江路 1516 弄",
        },
      ],
      table: [],
      text: "",
      date: "",
    };
  },
  mounted() {
    this.table = this.tableData;
  },
  methods: {
    cha() {
      if (this.text) {
        if (this.text) {
          this.table = this.tableData.filter((item) => {
            item.name.indexOf(this.text) != -1;
          });
        }
        console.log(this.table);
      } else {
        this.table = this.tableData;
      }
      
    },
    
  },
};
</script>

<style scoped>
.header {
  width: 100%;
  height: 200px;
  border: 1px solid black;
  display: flex;
  position: relative;
}
.header > div {
  margin: 50px 50px 0 50px;
}

.header button {
  width: 50px;
  height: 20px;
  position: absolute;
  right: 20px;
  bottom: 20px;
}
</style>
