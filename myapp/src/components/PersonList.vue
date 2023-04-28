<template>
  <div>
    <h1>Person List</h1>
    <!-- <b-table striped hover :items="items"></b-table> -->

    <div>
      <table class="table">
        <thead id="MainList">
            <tr>
              <th scope="col">Employee Number</th>
              <th scope="col">First Name</th>
              <th scope="col">Last Name</th>
              <th scope="col">Position</th>
              <th scope="col">Update</th>
              <th scope="col">Delete</th>
            </tr>
        </thead>
        <tbody v-for="id in items" v-bind:key="id">
          <tr>
            <th scope="row">{{ id.id }}</th>
            <td class="list-grou-item">{{ id.first_name }}</td>
            <td class="list--item">{{ id.last_name }}</td>
            <td class="list-grou-item">{{ id.position }}</td>
            <td class="list-grou-item">
              <a
                href="#"
                class="btn btn-primary"
                v-on:click="goToResume(id._id)"
                >View More</a
              >
            </td>
            <td class="list-grou-item">
              <a
                href="#"
                class="btn btn-danger"
                v-on:click="deleteClass(id._id)"
                >Delete</a
              >
            </td>
          </tr>
        </tbody>
      </table>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        items: [
          { id: 1, first_name: 'Jonathan', last_name: 'Yap', position: 'CEO' },
          { id: 2, first_name: 'Carl', last_name: 'Isip', position: 'CTO' },
          { id: 3, first_name: 'Chia', last_name: 'Hynson', position: 'Product Manager'},
          { id: 4, first_name: 'Fatima', last_name: 'Lazaro', position: 'Product Manager' },
        ]
      }
    },
    methods: {
      goToResume: function (id) {
        alert("Going to employee's resume...")
        this.$emit("update-employee", id);
      },
      deleteClass: function (id) {
        alert('Deleting Employee Data')
        this.$emit("delete-emplyee", id);
      },
    }  
  }
</script>