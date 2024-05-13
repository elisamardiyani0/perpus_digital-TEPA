<template>
  <div class="container-fluid">
    <div class="row">
      <h3 style="text-align: center;">DETAIL BUKU</h3>
      <div class="col-lg-2">
        <div class="card mt-5">
          <div class="card-body">
            <img :src="buku.cover" class="cover" alt="cover">
          </div>
        </div>
      </div>

      <div class="col-lg-4">
        <div class="row">
          <ul class="list-group list-group-flush" style="margin-top: 65px;">
            <li class="list-group-item">Judul: {{ buku.judul }}</li>
            <li class="list-group-item">
              <span v-if="buku.kategori">Kategori: {{ buku.kategori.nama }}</span>
              <span v-else>loading...</span>
            </li>

            <li class="list-group-item">Penulis: {{ buku.penulis }}</li>
            <li class="list-group-item">Penerbit: {{ buku.penerbit }}</li>
            <li class="list-group-item">Tahun Terbit: {{ buku.Tahun_terbit }}</li>
            <li class="list-group-item">Deskripsi: {{ buku.Deskripsi }}</li>
          </ul>
        </div>
      </div>
    </div>
  </div>

  <div class="d-flex justify-content-end">
        <nuxt-link to="/" class="btn btn-warning btn-lg rounded-5 px-5">BACK</nuxt-link>
  </div>

</template>

<script setup>
const supabase = useSupabaseClient();

const route = useRoute();

const buku = ref([]);

const getBookById = async () => {
  const {data, error} = await supabase.from('buku').select(`*, kategori(*)`).eq(`id`, route.params.id);
  if(data) buku.value = data[0];
}

onMounted(() => {
  getBookById();
});
</script>

<style scoped>
img {
  width: 100%;
}
</style>