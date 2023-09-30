<template>
  <div class="container-fluid my-5">
    <div class="row justify-content-center">
      <div class="col-12">
        <router-link
          :to="{ name: 'transaksi.create' }"
          class="btn btn-outline-success btn-sm rounded shadow mb-3"
          >Add
        </router-link>

        <div class="card rounded shadow">
          <div class="card-header">Daftar Transaksi</div>
          <div class="card-body">
            <table class="table">
              <thead>
                <tr class="text-center">
                  <th>Id</th>
                  <th>Username</th>
                  <th>Name</th>
                  <th>Phone</th>
                  <th>Location</th>
                  <th>Company Name</th>
                  <th>Website</th>
                  <th>Action</th>
                </tr>
              </thead>
              <tbody>
                <tr v-for="tr in transaksi" :key="tr.id">
                  <td>{{ tr.id }}</td>
                  <td>{{ tr.username }}</td>
                  <td>{{ tr.name }}</td>
                  <td>{{ tr.phone }}</td>
                  <td>{{ tr.address.city }}</td>
                  <!--tr.address.city  terjadi kerena address ini adalah sebuah objek-->
                  <td>{{ tr.company.name }}</td>
                  <!--tr.company.name  terjadi kerena company ini adalah sebuah objek-->
                  <td>{{ tr.website }}</td>
                  <td class="text-center">
                    <router-link
                      :to="{ name: 'transaksi.edit', params: { id: tr.id } }"
                      class="btn btn-outline-info btn-sm rounded shadow"
                      >Ubah</router-link
                    >
                    |
                    <div
                      class="btn btn-outline-danger btn-sm rounded shadow ml-3"
                    >
                      Hapus
                    </div>
                  </td>
                </tr>
              </tbody>
            </table>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import { onMounted, ref } from "vue";
export default {
  setup() {
    // reactive state
    let transaksi = ref([]);

    onMounted(() => {
      // get data from api endpoind
      axios
        .get("https://jsonplaceholder.typicode.com/users")
        // try catch
        .then((result) => {
          transaksi.value = result.data;
          console.log(result.data);
        })
        .catch((err) => {
          console.log(err.response.message);
        });
    });

    return {
      transaksi,
    };
  },
};
</script>