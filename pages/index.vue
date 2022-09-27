<template>
  <div>
    <v-container>
      <p class="text-h6">Here's the latest summary on your profile</p>
      <v-divider />
      <div>
        <p>Click the button to download all the data</p>
        <v-spacer />
        <v-btn prepend-icon="mdi-cloud-download" color="grey">Download</v-btn>
      </div>
      <el-table :data="tableData" stripe style="width: 100%">
        <el-table-column prop="name" label="Registrant" width="180" />
        <el-table-column prop="name" label="Status" width="180" />
        <el-table-column prop="payment" label="Last Payment" />
        <el-table-column prop="date" label="Last statement date" />
        <el-table-column prop="date" label="Account Settings" />
        <el-table-column prop="date" label="Membership status" />
      </el-table>

      <v-divider />
      <span> Our most frequently asked questions </span>
      <ul>
        <li v-for="(faq, index) in faqs" :key="index">
          <nuxt-link :to="faq.link">
            {{ faq.title }}
          </nuxt-link>
        </li>
      </ul>
      <v-divider />

      <v-row justify="start" no-gutters>
        <v-col>
          <v-avatar size="42px">
            <v-img
              alt="Avatar"
              src="https://avatars0.githubusercontent.com/u/9064066?v=4&s=460"
            ></v-img>
          </v-avatar>
        </v-col>
        <v-col>
          <p class="text-h6">Our fight for your rights</p>
          <p class="text-body-2">
            We stand behind the interest of creative community. This is
            reflected in our commitment to preserving long-term value of music
            and advocating on your behalf so that you are paid fairly. Learn
            more about the soe Advocacy work
          </p>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
import "element-plus/es/components/table/style/css";
import { ElTable } from "element-plus";
import { ElTableColumn } from "element-plus";

export default {
  components: {
    ElTable,
    ElTableColumn,
  },
  data() {
    return {
      tableData: [
        {
          date: "2016-05-03",
          name: "Valentine",
          address: "No. 189, Grove St, Los Angeles",
          payment: 9147,
        },
        {
          date: "2016-05-02",
          name: "Henry",
          address: "No. 189, Grove St, Los Angeles",
          payment: 1474,
        },
        {
          date: "2016-05-04",
          name: "Mark",
          address: "No. 189, Grove St, Los Angeles",
          payment: 314227,
        },
        {
          date: "2016-05-01",
          name: "Tom",
          address: "No. 189, Grove St, Los Angeles",
          payment: 1347,
        },
        {
          date: "2016-05-01",
          name: "Tom",
          address: "No. 189, Grove St, Los Angeles",
          payment: 1347,
        },
        {
          date: "2016-05-01",
          name: "Tom",
          address: "No. 189, Grove St, Los Angeles",
          payment: 1347,
        },
        {
          date: "2016-05-01",
          name: "Tom",
          address: "No. 189, Grove St, Los Angeles",
          payment: 1347,
        },
      ],
      faqs: [
        { title: "What is it that you want ?", link: "/faq/1" },
        { title: "What is it that you want ?", link: "/faq/2" },
        { title: "What is it that you want ?", link: "/faq/3" },
        { title: "What is it that you want ?", link: "/faq/4" },
      ],
    };
  },
};
</script>

<style>
</style>