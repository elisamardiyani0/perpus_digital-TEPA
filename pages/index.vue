<template>
    <div class="container-fluid">
        <div class="row my-5">
            <div class="col-lg-6">
                <nuxt-link to="/pengunjung/tambah">
                    <div class="card bg-pengunjung rounded-5">
                        <div class="card-body">
                            <h2>Pengunjung</h2>
                        </div>
                    </div>
                </nuxt-link>
            </div>

            <div class="col-lg-6">
                <nuxt-link to="/buku">
                    <div class="card bg-buku rounded-5">
                        <div class="card-body ">
                            <h2>Cari Buku</h2>
                        </div>
                    </div>
                </nuxt-link>
            </div>
            <h2 class="mt-5" style="font-family: ; margin-left= 150px;">STATISTIK</h2>
            <div class="col-lg-6">
                <div class="card kunjungan rounded-5 mt-5">
                    <div class="card-body text">
                        <h1>3</h1>
                        <h2 class="pt-5">Pengunjung</h2>
                    </div>
                </div>
            </div>

            <div class="col-lg-6">
                <div class="card buku rounded-5 mt-5">
                    <div class="card-body text">
                        <h1>180</h1>
                        <h2 class="pt-5">Buku</h2>
                    </div>
                </div>
            </div>

        </div>
    </div>
</template>


<style scoped>
.card {
    height: 250px;
    box-shadow: 1px 1px 10px #424242 ;
}
.card.bg-pengunjung{
    background-image: url('../assets/img/bg-kunjungan.jpeg');
    background-repeat: no-repeat;
    background-position: center center;
    background-size: cover;
    color: black;
    opacity: 25%;
}
.card.bg-buku{
    background: url('../assets/img/bg-home.jpg') no-repeat center center;
    background-size: cover;
    color: black;
    opacity: 25%;
}
.card.kunjungan{
    background-color:#EEE063 ;
}
.card.buku{
    background-color: #AEEEC7;
}
.text{
display: flex;
align-items: center;
}
.text> h1{
    font-size: 7rem;
}
h2 {
    font-weight: bold;
}

</style>