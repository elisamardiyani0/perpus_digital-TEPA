<template>
    <div class="container-fluid">
      <div class="row my-5">
        <div class="col-lg-6">
          <nuxt-link to="/pengunjung/tambah">
            <div class="card bg-pengunjung rounded-5 mt-5">
              <div class="card-body">
                <h2>Pengunjung</h2>
              </div>
            </div>
          </nuxt-link>
        </div>
  
        <div class="col-lg-6">
          <nuxt-link to="/buku">
            <div class="card bg-buku rounded-5 mt-5">
              <div class="card-body">
                <h2>Cari Buku</h2>
              </div>
            </div>
          </nuxt-link>
        </div>
        <div class="statistik rounded mb-7">
          <h1 class="ps-0 pt-5">STATISTIK</h1>
        </div>
  
        <div class="col-lg-6">
          <div class="card pengunjung rounded-5 mt-5">
            <div class="card-body text">
              <h1 class="ps-5">3</h1>
              <h2 class="pt-5 ps-5">Pengunjung</h2>
            </div>
          </div>
        </div>
  
        <div class="col-lg-6">
          <div class="card buku rounded-5 mt-5">
            <div class="card-body text">
              <h1 class="ps-5">180</h1>
              <h2 class="pt-5 ps-4">Buku</h2>
            </div>
          </div>
        </div>
      </div>
    </div>
  
    <div class="row mt-3">
      <div class="col-md-6">
        <div class="card-body">
          <!-- <Bar :options="chartOptions" :data="chartData"></Bar> -->
          <canvas id="myChart"></canvas>
        </div>
      </div>
    </div>
  </template>

<script setup>
import {Chart} from 'chart.js'

const labels = [
    'January',
    'February',
    'March',
    'April',
    'May',
    'June',
  ];

  const data = {
    labels: "Statistik p",
    datasets: [{
      label: 'My First dataset',
      backgroundColor: ["#5B96AF","#7FB2C8","#20B5F4","#A5DAF1","#3F85A4","#09638A"],
      borderColor: 'rgb(255, 99, 132)',
      data: [0, 10, 5, 2, 20, 30, 45],
    }]
  };

  const config = {
    type: 'bar',
    data: data,
    options: {}
  };

  onMounted(() => {
    const myChart = new Chart(
    document.getElementById('myChart'),
    config
  );
  })
</script>

  <!-- <script>
  import { Bar } from 'vue-chartjs'
  import { Chart, Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale } from 'chart.js'

  Chart.register(Title, Tooltip, Legend, BarElement, CategoryScale, LinearScale)

    
    export default {
      name: "BarChart",
      components: { Bar },
      data() {
        return {
          chartData: {
            labels: ["January", "February", "March", "April", "May", "June", "July", "August", "September", "October", "November", "December"],
            datasets: [
              {
                label: "",
                data: [80, 20, 60, 25, 45, 17, 55, 100, 59, 35, 25, 79],
                backgroundColor: ["#F03C3C", "#EFE059", "#61905A", "#A68273", "#3E8DD6", "#43DDD4"],
              },
            ],
          },
          chartOptions: {
            responsive: true,
            maintainAspectRatio: false,
            aspectRatio: 0.7,
          },
        };
      },
    };
    </script> -->
    
    <style scoped>
    .card {
      height: 250px;
      box-shadow: 1px 1px 10px #424242;
    }
    .card.bg-pengunjung {
      background-image: url("../assets/img/bg-kunjungan.jpg");
      background-repeat: no-repeat;
      background-position: center center;
      background-size: cover;
      color: #0c0101;
      opacity: 50%;
    }
    .card.bg-buku {
      background: url("../assets/img/bg-home.jpg") no-repeat center center;
      background-size: cover;
      color: #180101;
      opacity: 50%;
    }
    .card.pengunjung {
      background-color: #f3eebb;
    }
    .card.buku {
      background-color: #c5fbc0;
    }
    .text {
      display: flex;
    
      align-items: center;
    }
    .text > h1 {
      font-size: 7rem;
    }
  </style>