<template>
  <nav class="navbar navbar-expand-lg navbar-light bg-info mb-3">
    <div class="container">
      <a class="navbar-brand" href="#">Iron Temple Storefront</a>
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbarSupportedContent"
        aria-controls="navbarSupportedContent"
        aria-expanded="false"
        aria-label="Toggle navigation"
      >
        <span class="navbar-toggler-icon"></span>
      </button>
      <div
        class="collapse navbar-collapse justify-content-end"
        id="navbarSupportedContent"
      >
        <ul class="navbar-nav mb-2 mb-lg-0 mr-auto">
          <li class="nav-item">
            <a class="btn btn-primary me-3 active" aria-current="page" href="/"
              >Home</a
            >
          </li>
          <li class="nav-item">
            <a class="btn btn-primary me-3 position-relative" href="/cart"
              >Cart
              <span
                id="badge"
                class="position-absolute top-0 start-100 translate-middle badge rounded-pill bg-danger"
              ></span
            ></a>
          </li>
          <li class="nav-item">
            <!-- Button trigger modal -->
            <button
              type="button"
              class="btn btn-primary"
              data-bs-toggle="modal"
              data-bs-target="#addProductModal"
            >
              Add a product
            </button>

            <!-- Modal -->
            <div
              class="modal fade"
              id="addProductModal"
              tabindex="-1"
              aria-labelledby="exampleModalLabel"
              aria-hidden="true"
            >
              <div class="modal-dialog">
                <div class="modal-content">
                  <div class="modal-header">
                    <h5 class="modal-title" id="exampleModalLabel">
                      Add product
                    </h5>
                    <button
                      type="button"
                      class="btn-close"
                      data-bs-dismiss="modal"
                      aria-label="Close"
                    ></button>
                  </div>
                  <div class="modal-body">
                    <div class="mb-3">
                      <label for="addTitle" class="form-label">Title</label>
                      <input
                        class="form-control"
                        type="text"
                        name="addTitle"
                        id="addTitle"
                      />
                    </div>
                    <div class="mb-3">
                      <label for="" class="form-label">Category</label>
                      <select
                        class="form-select"
                        name="addCategory"
                        id="addCategory"
                      >
                        <option value="Calisthenics">Calisthenics</option>
                        <option value="Weightlifting">Weightlifting</option>
                        <option value="Resistance">Resistance</option>
                      </select>
                    </div>
                    <div class="mb-3">
                      <label for="addPrice" class="form-label">Price</label>
                      <input
                        class="form-control"
                        type="text"
                        name="addPrice"
                        id="addPrice"
                      />
                    </div>
                    <div class="mb-3">
                      <label for="addImg" class="form-label">Image URL</label>
                      <input
                        class="form-control"
                        type="text"
                        name="addImg"
                        id="addImg"
                      />
                    </div>
                  </div>
                  <div class="modal-footer">
                    <button
                      type="button"
                      class="btn btn-secondary"
                      data-bs-dismiss="modal"
                    >
                      Close
                    </button>
                    <button
                      type="button"
                      class="btn btn-primary"
                      data-bs-dismiss="modal"
                      onclick="createProduct()"
                    >
                      Create Product
                    </button>
                  </div>
                </div>
              </div>
            </div>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<script>
export default {};
</script>

<style lang=""></style>
