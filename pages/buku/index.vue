<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-lg-12">
                <h2 class="text-center my-4"></h2>
                <div class="my-3">
                    <input type="search" class="form-control rounded-5" placeholder="Mau baca apa hari ini?">
                </div>
                <div class="my-3 text-muted ">menampilkan 3 dari 3</div>
                <div class="row">
                    <div class="col-lg-2">
                        <div class="card mb-3">
                            <div class="card-body">
                                <img src="~/assets/img/gambar1.jpeg" class="gambar" alt="gambar1">
                            </div>
                        </div>
                    </div>
                    <div class="col-lg-2">
                        <div class="card-3">
                            <div class="card-body">
                                <img src="~/assets/img/gambar2.jpeg" class="gambar" alt="gambar2">
                            </div>
                        </div>
                    </div>
                    <div class="col-lg-2">
                        <div class="card mb-3">
                            <div class="card-body">
                                <img src="~/assets/img/gambar3.jpg" class="gambar" alt="gambar3">
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <div class="d-flex justify-content-end">
        <nuxt-link to="/" class="btn btn-warning btn-lg rounded-5 px-5">BACK</nuxt-link>
    </div>
</template>

<style scoped>
.card-body{
    width: 100%;
    height: 20em;
    padding: 0;
    box-shadow: 1px 1px 10px #403610;
}
.gambar{
    width: 100%;
    height: 100%;
    object-fit: gambar;
    object-position: 0 30;
}
.btn-warning{
    box-shadow: 1px 1px 10px #403610;
}
</style>