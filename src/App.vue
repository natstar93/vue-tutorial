<template>
  <div id="app" class="small-container">
    <h1>Employees</h1>
    <employee-table :employees="employees" />
    <employee-form @add:employee="addEmployee" />
  </div>
</template>

<script>
import EmployeeTable from "@/components/EmployeeTable.vue";
import EmployeeForm from "@/components/EmployeeForm.vue";

export default {
  name: "App",
  components: {
    EmployeeTable,
    EmployeeForm
  },
  data() {
    return {
      employees: [
        {
          id: 0,
          name: "Nat",
          email: "nat@piedpiper.com"
        },
        {
          id: 1,
          name: "Bertram Gilfoyle",
          email: "gilfoyle@piedpiper.com"
        },
        {
          id: 2,
          name: "Dinesh Chugtai",
          email: "dinesh@piedpiper.com"
        }
      ]
    };
  },
  methods: {
    addEmployee(employee) {
      const id = this.employees.length;
      this.employees = [...this.employees, { ...employee, id }];
    }
  }
};
</script>

<style>
button {
  background: #009435;
  border: 1px solid #009435;
}

.small-container {
  max-width: 680px;
}
</style>
