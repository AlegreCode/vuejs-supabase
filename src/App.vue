<template>
  <div class="container">
    <div class="row pt-5">
      <div class="col-3">
        <div class="card">
          <div class="card-body">
            <h2 class="display-5 text-center">Subir Imágen</h2>
            <form>
              <div class="form-group mb-3 text-center">
                <img src="https://fakeimg.pl/200x200/?text=IMG" alt="vista previa" class="img-thumbnail">
              </div>
              <div class="form-group mb-3">
                <label for="formFile" class="form-label">Imágen</label>
                <input class="form-control" type="file" id="formFile">
              </div>
              <div class="form-group mb-3">
                <label for="title">Título</label>
                <input type="text" class="form-control" id="title">
              </div>
              <div class="form-group d-grid">
                <button type="submit" class="btn btn-primary">Subir</button>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
