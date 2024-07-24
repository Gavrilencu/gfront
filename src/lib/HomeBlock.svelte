<script>
  import medii from "$lib/img/teste.webp";
  import teste from "$lib/img/teste.jpeg";
  import echipamente from "$lib/img/echipamente.png";
  import logo from "$lib/img/logo.png";
  import {goto} from "$app/navigation"
</script>

<div class="container py-4">


  <div class="p-5 mb-4 bg-light rounded-3" >
    <div class="container-fluid py-5 " >
      <h1 class="display-5 fw-bold">GMM BIOTECHNOLOGY</h1>
      <p class="col-md-8 fs-4">
        Oferim un portofoliu extins de produse, inclusiv reactive, kituri de
        testare și echipamente de laborator, pentru a satisface nevoile variate
        ale spitalelor și laboratoarelor din Moldova.
      </p>
      <button class="btn btn-primary btn-lg" type="button" on:click={() => {
        goto("/contacte")
      }}
        >Contacteaza-ne</button
      >
    </div>
  </div>

  <div class="row align-items-md-stretch">
    <div class="col-md-6">
      <div class="h-100 p-5 text-white rounded-3 bgcolor">
        <h2>Teste PCR</h2>
        <p>
          Ne străduim să fim partenerul de încredere al spitalelor și
          laboratoarelor din Moldova, oferindu-le soluții integrate și suport
          tehnic specializat pentru implementarea eficientă a testelor PCR.
        </p>
        <a href="/teste" class="btn btn-outline-light" type="button"
          >Acceseaza</a
        >
      </div>
    </div>
    <div class="col-md-6 ">
      <div class="h-100 p-5 bg-light text-white border rounded-3 bgcolor">
        <h2>Medii de cultura</h2>
        <p>
          Suntem partenerul ideal pentru instituțiile medicale din Moldova,
          furnizând produse de cea mai înaltă calitate, precum și asistență
          tehnică specializată.
        </p>
        <a href="/cromogen" class="btn btn-outline-light" type="button"
          >Acceseaza</a
        >
      </div>
    </div>
  </div>
  <div class="position-relative overflow-hidden p-3 p-md-1 m-md-1 text-center bg-light">
    <div class="col-md-5 p-lg-2 mx-auto my-1">
      <h1 class="display-4 fw-normal">Medii nutriente:</h1>
      <p class="lead fw-normal">Medii utilizate pentru creșterea microorganismelor în laborator, conținând nutrienți esențiali precum aminoacizi, carbohidrați și săruri minerale.</p>
      <a class="btn btn-primary btn-lg" href="/nutrient">Medii Nutriente</a>
    </div>
    <div class="product-device shadow-sm d-none d-md-block"></div>
    <div class="product-device product-device-2 shadow-sm d-none d-md-block"></div>
  </div>
  <footer class="pt-3 mt-4 text-muted border-top">© 2024</footer>
</div>


<style>
  .bgcolor {
    background-color: rgb(65, 97, 238) !important;
  }
  .position-relative {

    margin-top: 20px !important;
  }
  .descriptionProdus {
    width: 100%;
    display: flex;
    justify-content: center;
    padding: 10px;
    text-align: center;
  }
  .imgProdus {
    width: 100%;
    height: 250px;
    border-radius: 5px;
    object-fit: cover;
  }
  .nameOfProdus {
    width: 100%;
    display: flex;
    justify-content: center;
  }
  .produs {
    width: 350px;
    height: 400px;
    display: flex;
    box-shadow: 0px 0px 4px rgb(203, 228, 253);
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
    margin-inline: 50px;
    border-radius: 5px;

    background-color: white;
  }
  .block {
    width: 100%;
    padding: 30px;
    display: flex;
    align-items: center;
    justify-content: center;
    height: 100%;
    margin-top: 30px;
    flex-wrap: wrap;
  }
  .infoName {
    width: 100%;
    text-align: center;
  }
  .infoblock {
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: start;
    flex-direction: column;
    margin-top: 10px;
  }
  * {
    font-family: "Trebuchet MS", "Lucida Sans Unicode", "Lucida Grande",
      "Lucida Sans", Arial, sans-serif;
  }
  @media screen and (max-width: 1300px) {
    .produs {
      margin-bottom: 20px;
    }
    .block {
      padding: 0px;
    }
  }
  @media screen and (max-width: 600px) {
    .produs {
      width: 100% !important;
    }
  }
</style>
