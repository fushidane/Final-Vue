<template>
  <div class="container">
    <h1>Users List</h1>
    <table>
      <thead>
        <tr>
          <th>ID</th>
          <th>Full Name</th>
          <th>Email</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="user in users" :key="user.id">
          <td>{{ user.id }}</td>
          <td>{{ user.full_name }}</td>
          <td>{{ user.email }}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script setup>
const users = [
{
        "id": 1,
        "full_name": "John Doe",
        "email": "john@example.com"
      },
      {
        "id": 2,
        "full_name": "Jane Smith",
        "email": "jane@example.com"
      },
      {
        "id": 3,
        "full_name": "Alice Johnson",
        "email": "alice@example.com"
      },
      {
        "id": 4,
        "full_name": "Bob Williams",
        "email": "bob@example.com"
      },
      {
        "id": 5,
        "full_name": "Emily Brown",
        "email": "emily@example.com"
      },
      {
        "id": 6,
        "full_name": "Michael Davis",
        "email": "michael@example.com"
      },
      {
        "id": 7,
        "full_name": "Olivia Wilson",
        "email": "olivia@example.com"
      },
      {
        "id": 8,
        "full_name": "William Taylor",
        "email": "william@example.com"
      },
      {
        "id": 9,
        "full_name": "Sophia Martinez",
        "email": "sophia@example.com"
      },
      {
        "id": 10,
        "full_name": "Daniel Anderson",
        "email": "daniel@example.com"
      },
      {
        "id": 11,
        "full_name": "Ava Thomas",
        "email": "ava@example.com"
      },
      {
        "id": 12,
        "full_name": "James Garcia",
        "email": "james@example.com"
      },
      {
        "id": 13,
        "full_name": "Isabella Lopez",
        "email": "isabella@example.com"
      },
      {
        "id": 14,
        "full_name": "Liam Hernandez",
        "email": "liam@example.com"
      },
      {
        "id": 15,
        "full_name": "Mia Martinez",
        "email": "mia@example.com"
      },
      {
        "id": 16,
        "full_name": "Alexander Adams",
        "email": "alexander@example.com"
      },
      {
        "id": 17,
        "full_name": "Charlotte Young",
        "email": "charlotte@example.com"
      },
      {
        "id": 18,
        "full_name": "Elijah Scott",
        "email": "elijah@example.com"
      },
      {
        "id": 19,
        "full_name": "Abigail Lewis",
        "email": "abigail@example.com"
      },
      {
        "id": 20,
        "full_name": "Evelyn King",
        "email": "evelyn@example.com"
      }
];
</script>

<style scoped>
.container {
  width: 1200px;
  margin: 0 auto;
  padding: 3%;
  text-align: center;
  background: linear-gradient(135deg, #235789, #8aaebd);
  border-radius: 10px;
  box-shadow: 0 0 20px rgba(0, 0, 0, 0.2);
  display: flex;
  flex-direction: column;
  justify-content: center;
}

h1 {
  color: #fff;
  font-size: x-large;
  font-weight: 800;
}

table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
}

th, td {
  border: 1px solid #fff;
  padding: 8px;
  color: #fff;
}

th {
  background-color: #235789;
}

tbody tr:nth-child(even) {
  background-color: #8aaebd;
}

tbody tr:nth-child(odd) {
  background-color: #235789;
}
</style>
