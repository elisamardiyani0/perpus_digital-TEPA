<template>
    <div class="container-fluid">
        <div class="row">
            <div class="col-lg-12">
                <h2 class="text-center my-4">RIWAYAT KUNJUNGAN</h2>
                <div class="my-3">
                    <input type="search" class="form-control form-control-lg rounded-5" placeholder="filter...">
                </div>
                 <div class="my-3 text-muted">menampilkan {{ visitors.length }} dari {{ hasil }}</div>
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
                        <tr v-for="(visitor,i) in visitors" :key="i">
                            <td>{{ i+1 }}.</td>
                            <td>{{ visitor.nama }}</td>
                            <td>{{ visitor.keanggotaan.nama }}</td>
                            <td>{{ visitor.tanggal}},{{ visitor.waktu }}</td>
                            <td>{{ visitor.keperluan.nama }}</td>
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

<script setup>
const supabase = useSupabaseClient()
const visitors = ref([])
const keyword = ref('')
const hasil = ref([])

const getPengunjung = async () => {
    const {data,error } = await supabase.from('pengunjung').select(`*,keanggotaan(*),keperluan(*)`)
    .ilike('nama', `%${keyword.value}`)
    .order('id', {ascending: false})
    if(data) visitors.value = data
}
const pengunjung = async () => {
    const {data, count} = await supabase.from('pengunjung').select(`*`, {count: 'exact'})
    if  (data) hasil.value = count
}

onMounted(() =>{
        getPengunjung()
        pengunjung()
    })
</script>

<style scoped>
.btn-warning{
    box-shadow: 1px 1px 10px #403610 !important;
}
</style>