<template>
  <div class="container my-5">
    <div class="row justify-content-center">
      <div class="col-8">
        <router-link
          :to="{ name: 'transaksi.index' }"
          class="btn btn-outline-danger btn-sm mb-3 shadow"
          >Back
        </router-link>
        <div class="card shadow">
          <div class="card-header">Tamabah Transaksi</div>
          <div class="card-body">
            <form action="">
              <div class="mb-3">
                <label for="title" class="form-label">Username</label>
                <input type="text" class="form-control" />
                <div class="text-danger">validation Mesage</div>
              </div>
              <div class="mb-3">
                <label for="title" class="form-label">Name</label>
                <input type="text" class="form-control" />
                <div class="text-danger">validation Mesage</div>
              </div>
              <div class="mb-3">
                <label for="title" class="form-label">phone</label>
                <input type="text" class="form-control" />
                <div class="text-danger">validation Mesage</div>
              </div>
              <div class="mb-3 btn btn-outline-primary btn-sm rounded shadow">
                submit
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// reactive digunakan untuk data binding
import { reactive,ref } from "vue";

export default {};
</script>