<template>
  <section>
    <div class="container d-flex justify-content-center mb-3 pt-4">
      <div class="d-flex w-25 ms-3">
        <label for="" class="form-label">Sort by category</label>
        <select
          class="form-select"
          name=""
          id="sortCategory"
          onchange="sortCategory()"
        >
          <option value="All">All</option>
          <option value="Calisthenics">Calisthenics</option>
          <option value="Weightlifting">Weightlifting</option>
          <option value="Resistance">Resistance</option>
        </select>
      </div>
      <div class="d-flex w-25 ms-3">
        <label for="" class="form-label">Sort name</label>
        <select class="form-select" name="" id="sortName" onchange="sortName()">
          <option value="ascending">Ascending</option>
          <option value="descending">Descending</option>
        </select>
      </div>
      <div class="d-flex w-25 ms-3">
        <label for="" class="form-label">Sort price</label>
        <select
          class="form-select"
          name=""
          id="sortPrice"
          onchange="sortPrice()"
        >
          <option value="ascending">Ascending</option>
          <option value="descending">Descending</option>
        </select>
      </div>
    </div>
    <div id="products" class="container d-flex mb-3"></div>
  </section>
</template>

<script>
export default {
  name: "joe",
  components: {},
  mounted: function() {
    let products = JSON.parse(localStorage.getItem("products"))
      ? JSON.parse(localStorage.getItem("products"))
      : [
          {
            title: "Fender CC-60S Concert Acoustic Guitar",
            category: "Guitars",
            price: 2899.99,
            img: "https://m.media-amazon.com/images/I/71q0c+1KWqL._AC_SL1500_.jpg",
          },
          {
            title: "Striped Series Frankie Electric Guitar",
            category: "Guitars",
            price: 3799.99,
            img: "https://m.media-amazon.com/images/I/710AH9B1qWL._AC_SL1500_.jpg",
          },
          {
            title: "Casio CT-X700 61-Key Portable Keyboard",
            category: "Keyboards",
            price: 2999.99,
            img: "https://m.media-amazon.com/images/I/61-33qITONL._AC_SL1101_.jpg",
          },
          {
            title: "Roland GO:PIANO 88-Key Full Size Portable Digital Piano Keyboard ",
            category: "Keyboards",
            price: 6400,
            img: "https://m.media-amazon.com/images/I/71iLuY0PIyS._AC_SL1500_.jpg",
          },
          {
            title: "Fender 6 String Acoustic-Electric Guitar",
            category: "Guitars",
            price: 3199.99,
            img: "https://m.media-amazon.com/images/I/61LEIkXEdbL._AC_SL1500_.jpg",
          },
          {
            title: "Drum Set Eastar 22 inch for Adults, 5 Piece Full Size Drum Kit",
            category: "Drums",
            price: 8999.99,
            img: "https://m.media-amazon.com/images/I/71nJgkQau1L._AC_SL1500_.jpg",
          },
          {
            title: "Pyle 3-Piece Kids Drum Set - 13 Complete Junior Drummer Kit with Wooden Shells, Bass & Foot Pedal, Snare, Tom, Cymbal w/Stand, Pair of Drumsticks",
            category: "Drums",
            price: 6499.99,
            img: "https://m.media-amazon.com/images/I/81xkvpb+0ZL._AC_SL1500_.jpg",
          },
          {
            title: "Casio Casiotone, 61-Key Portable Keyboard with USB",
            category: "Keyboards",
            price: 2599.99,
            img: "https://m.media-amazon.com/images/I/51maJm7NdgL._AC_SL1024_.jpg",
          },
        ];

    let cart = JSON.parse(localStorage.getItem("cart"))
      ? JSON.parse(localStorage.getItem("cart"))
      : [];

    // READ
    function readProducts(products) {
      document.querySelector("#products").innerHTML = "";
      products.forEach((product, position) => {
        document.querySelector("#products").innerHTML += `
      <div class="card">
        <img src="${product.img}" class="card-img-top" alt="${product.title}">
        <div class="card-body" style="background-color: transparent;">
          <h5 class="card-title">${product.title}</h5>
          <p class="card-text">R${product.price}</p>
          <div class="d-flex mb-3">
            <input type="number" class="form-control" value=1 min=1 id="addToCart${position}">
            <button type="button" class="btn btn-secondary ms-3" onclick="addToCart(${position})"><i class="fas fa-cart-plus"></i></button>
          </div>
          
          
          \\
          </div>
          <div class="d-flex justify-content-end card-footer">
            <button type="button" class="btn btn-primary w-50" data-bs-toggle="modal" data-bs-target="#editProduct${position}"><i class="bi bi-pencil" style="color:white"></i></button>
            <button type="button" class="btn btn-danger w-50 ms-3" onclick="deleteProduct(${position})" ><i class="bi bi-trash" style="color:white"></i></button>
          </div>
      </div>






      <div
                class="modal fade"
                id="editProduct${position}"
                tabindex="-1"
                aria-labelledby="exampleModalLabel"
                aria-hidden="true"
              >
                <div class="modal-dialog">
                  <div class="modal-content">
                    <div class="modal-header">
                      <h5 class="modal-title" id="exampleModalLabel">
                        Edit ${product.title}
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
                        <label for="editTitle${position}" class="form-label">Title</label>
                        <input
                          class="form-control"
                          type="text"
                          name="editTitle${position}"
                          id="editTitle${position}"
                          value="${product.title}"
                        />
                      </div>
                      <div class="mb-3">
                        <label for="editCategory${position}" class="form-label">Category</label>
                        <select
                          class="form-select"
                          name="editCategory${position}"
                          id="editCategory${position}"
                        >
                          <option value="Calisthenics">Calisthenics</option>
                          <option value="Weightlifting">Weightlifting</option>
                          <option value="Resistance">Resistance</option>
                        </select>
                      </div>
                      <div class="mb-3">
                        <label for="editPrice${position}" class="form-label">Price</label>
                        <input
                          class="form-control"
                          type="text"
                          name="editPrice${position}"
                          id="editPrice${position}"
                          value="${product.price}"
                        />
                      </div>
                      <div class="mb-3">
                        <label for="editImg${position}" class="form-label">Image URL</label>
                        <input
                          class="form-control"
                          type="text"
                          name="editImg${position}"
                          id="editImg${position}"
                          value="${product.img}"
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
                        onclick="updateProduct(${position})"
                      >
                        Save changes
                      </button>
                    </div>
                  </div>
                </div>
              </div>
    `;
      });
    }

    readProducts(products);
    showCartBadge();

    // CREATE
    function createProduct() {
      let title = document.querySelector("#addTitle").value;
      let category = document.querySelector("#addCategory").value;
      let price = document.querySelector("#addPrice").value;
      let img = document.querySelector("#addImg").value;

      try {
        if (!title || !price || !img)
          throw new Error("Please fill in all fields");
        products.push({
          title,
          category,
          price,
          img,
        });
        localStorage.setItem("products", JSON.stringify(products));
        readProducts(products);
      } catch (err) {
        alert(err);
      }
    }

    // UPDATE
    function updateProduct(position) {
      let title = document.querySelector(`#editTitle${position}`).value;
      let category = document.querySelector(`#editCategory${position}`).value;
      let price = document.querySelector(`#editPrice${position}`).value;
      let img = document.querySelector(`#editImg${position}`).value;

      try {
        if (!title || !price || !img)
          throw new Error("Please fill in all fields");
        products[position] = {
          title,
          category,
          price,
          img,
        };
        localStorage.setItem("products", JSON.stringify(products));
        readProducts(products);
      } catch (err) {
        alert(err);
      }
    }

    // DELETE
    function deleteProduct(position) {
      let confirmation = confirm(
        "Are you sure you want to delete the selected product?"
      );

      if (confirmation) {
        products.splice(position, 1);
        localStorage.setItem("products", JSON.stringify(products));
        readProducts(products);
      }
    }

    // ADD TO CART
    function addToCart(position) {
      let qty = document.querySelector(`#addToCart${position}`).value;
      let added = false;
      cart.forEach((product) => {
        if (product.title == products[position].title) {
          alert(
            `You have successfully added ${qty} ${products[position].title} to the cart`
          );
          product.qty = parseInt(product.qty) + parseInt(qty);
          added = true;
        }
      });
      if (!added) {
        cart.push({ ...products[position], qty });
        alert(
          `You have successfully added ${qty} ${products[position].title} to the cart`
        );
      }

      showCartBadge();

      localStorage.setItem("cart", JSON.stringify(cart));
    }

    // Update Cart Badge
    function showCartBadge() {
      document.querySelector("#badge").innerHTML = cart ? cart.length : "";
    }

    // SORT BY CATEGORY
    function sortCategory() {
      let category = document.querySelector("#sortCategory").value;

      if (category == "All") {
        return readProducts(products);
      }

      let foundProducts = products.filter((product) => {
        return product.category == category;
      });

      readProducts(foundProducts);
      console.log(foundProducts);
    }

    // SORT BY NAME

    function sortName() {
      let direction = document.querySelector("#sortName").value;

      let sortedProducts = products.sort((a, b) => {
        if (a.title.toLowerCase() < b.title.toLowerCase()) {
          return -1;
        }
        if (a.title.toLowerCase() > b.title.toLowerCase()) {
          return 1;
        }
        return 0;
      });
      if (direction == "descending") sortedProducts.reverse();
      console.log(sortedProducts);
      readProducts(products);
    }

    // SORT BY PRICE

    function sortPrice() {
      let direction = document.querySelector("#sortPrice").value;

      let sortedProducts = products.sort((a, b) => a.price - b.price);

      console.log(sortedProducts);

      if (direction == "descending") sortedProducts.reverse();
      readProducts(sortedProducts);
    }
  },
};
</script>

<style>
section {
  /* background-image: url("../assets/images/logos/de-an-sun-b57RqS-nQ1c-unsplash.jpg"); */
  background-size: cover;
  background: #4d4d4d;
  height: 120vh;
}

.form-label {
  color: white
}

.card-img-top {
  width: 100%;
  object-fit: cover;
}

.card-img-top:hover {
  height: 400px;
  width: 400px;
}

</style>
