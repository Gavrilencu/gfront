<script>
        import { onMount } from "svelte";
    import EditModal from "../../lib/EditModal.svelte"; // Schimbă importul la noua componentă

    let products = [];
    let selectedProduct = null;

    async function fetchProducts() {
        const response = await fetch("/api/products");
        products = await response.json();
        // Decodăm fiecare imagine a produselor pentru a fi afișată
        products.forEach(product => {
            if (product.image) {
                product.imageUrl = `data:image/jpeg;base64,${product.image}`;
            }
        });
    }
    onMount(() => {
        fetchProducts();
    });
    export let productId;
    $: console.log(productId)

    async function deleteProduct() {
        const response = await fetch(`/api/products/${productId}`, {
            method: "DELETE",
        });

        if (response.ok) {
            fetchProducts();
        }
    }
</script>

<nav class="navbar navbar-expand-lg navbar-dark bg-dark">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">GMM</a>
      <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarNavDarkDropdown" aria-controls="navbarNavDarkDropdown" aria-expanded="false" aria-label="Toggle navigation">
        <span class="navbar-toggler-icon"></span>
      </button>
      <div class="collapse navbar-collapse" id="navbarNavDarkDropdown">
        <ul class="navbar-nav">
          <li class="nav-item dropdown">
            <a class="nav-link dropdown-toggle" href="#" id="navbarDarkDropdownMenuLink" role="button" data-bs-toggle="dropdown" aria-expanded="false">
              Meniu
            </a>
            <ul class="dropdown-menu dropdown-menu-dark" aria-labelledby="navbarDarkDropdownMenuLink">
              <li> <a class="dropdown-item" href="/">Pagina principala</a></li>
              <li>    <a class="dropdown-item" href="/getProducts">Vizualizați Produsele</a></li>
              <li>    <a class="dropdown-item" href="/addProduct">Adaugă Produs</a></li>
              <li>        <a class="dropdown-item" href="/deleteProduct">Sterge Produs</a></li>
            </ul>
          </li>
        </ul>
      </div>
    </div>
  </nav>
  {#each [...new Set(products.map(prod => prod.category))] as category}
    <h3>{category}</h3>
    <div class="product-grid">
        {#each products.filter(prod => prod.category === category) as product}
            <div class="product-box" on:mouseenter={() => {productId = product?.id}}>
                <h4>{product.name}</h4>
                <p>Cod: {product.code}</p>
                {#if product.imageUrl}
                    <img src={product.imageUrl} alt={`Imaginea produsului ${product.name}`} class="product-image"/>
                {/if}
                <button on:click={deleteProduct}>Șterge Produs</button>
            </div>
        {/each}
    </div>
{/each}


<style>
    .product-grid {
        display: grid;
        grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
        grid-gap: 10px;
    }

    .product-box {
        border: 1px solid #ccc;
        padding: 10px;
        overflow: hidden;
        cursor: pointer;
        transition: background-color 0.3s;
    }

    .product-box:hover {
        background-color: #f0f0f0;
    }
 
    .product-image {
        max-width: 100%; 
        height: auto;
    }
    .navbar {
        background-color: rgb(8, 94, 165) !important;
    }
</style>