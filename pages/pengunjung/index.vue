<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-lg-12">
                <h2 class="text-center my-4">RIWAYAT KUNJUNGAN</h2>
                <div class="my-3">
                    <input type="search" class="form-control form-control-lg rounded-5" placeholder="filter...">
                </div>
                 <div class="my-3 text-muted">menampilkan 1 dari 1</div>
                 <table class="table">
                    <thead>
                        <tr>
                            <td>#</td>
                            <td>NAMA</td>
                            <td>KEANGGOTAAN</td>
                            <td>WAKTU</td>
                            <td>KEPERLUAN</td>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td>1.</td>
                            <td>R.Tini Gantini</td>
                            <td>Guru</td>
                            <td>27 februari 2024, 09.22.13</td>
                            <td>Baca</td>

                        </tr>
                    </tbody>
                 </table>
            </div>
        </div>
    </div>
    <div class="d-flex justify-content-end">
        <nuxt-link to="/" class="btn btn-warning btn-lg rounded-5 px-5">BACK</nuxt-link>
    </div>
</template>