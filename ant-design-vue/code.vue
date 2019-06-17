<template>
  <a-table :columns="columns" :dataSource="data" bordered>
    <a slot="name" slot-scope="text" href="javascript:;">{{text}}</a>
    <a slot="age" slot-scope="text" href="songzmin">{{text}}</a>
    <span slot="customTitle">
      <a-icon type="smile-o"/>Name
    </span>
    <span slot="tags" slot-scope="tags">
      <a href="javascript">{{tags}}</a>
      <!-- tags:这里其实对应该条记录的tags值，也就是tags:["nice", "developer"] -->
      <!-- <a-tag v-for="tag in tags" color="blue" :key="tag">{{tag}}</a-tag> -->
    </span>
    <span slot="actions" slot-scope="text">
      <a href="javascript:;">Invite 一 {{text.name}}</a>
      <a-divider type="vertical"/>
      <a href="javascript:;">Delete</a>
      <a-divider type="vertical"/>
      <a href="javascript:;" class="ant-dropdown-link">
        More actions
        <a-icon type="down"/>
      </a>
    </span>
  </a-table>
</template>
<script>
const columns = [
  {
    dataIndex: "name",
    key: "name",
    slots: { title: "customTitle" },
    scopedSlots: { customRender: "name" }
  },
  {
    title: "Age",
    key: "age",
    dataIndex: "age",
    scopedSlots: { customRender: "age" }
  },
  {
    title: "Address",
    dataIndex: "address",
    key: "address"
  },
  {
    title: "Tags",
    key: "tags",
    dataIndex: "tags",
    scopedSlots: { customRender: "tags" }
  },
  {
    title: "Action",
    key: "actions",
    scopedSlots: { customRender: "actions" }
  }
];

const data = [
  {
    key: "1",
    name: "John Brown",
    age: 32,
    address: "New York No. 1 Lake Park",
    tags: ["nice", "developer"]
  },
  {
    key: "2",
    name: "Jim Green",
    age: 42,
    address: "London No. 1 Lake Park",
    tags: ["loser"]
  },
  {
    key: "3",
    name: "Joe Black",
    age: 32,
    address: "Sidney No. 1 Lake Park",
    tags: ["cool", "teacher"]
  }
];

export default {
  data() {
    return {
      data,
      columns
    };
  }
};
</script>