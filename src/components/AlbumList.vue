<template>
  <div>
    <h2 style="color: pink ; text-align: center; font-weight: bold;">Albums</h2>
    <div v-if="albums.length">
      <table class="album-table">
        <tbody>
          <tr v-for="album in albums" :key="album.id" @click="viewAlbum(album.id)" class="album-item" style="cursor: pointer;">
            <td class="album-id">{{ album.id }}</td>
            <td class="album-title">{{ album.title }}</td>
          </tr>
        </tbody>
      </table>
    </div>
    <div v-else style="text-align: center; margin-top: 20px;">
      <p>No albums available.</p>
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue'
import { useAlbumsStore } from '../stores/albums'
import { useRouter } from 'vue-router'

const albumsStore = useAlbumsStore()
const albums = ref([])
const router = useRouter()

const fetchAlbums = async () => {
  await albumsStore.fetchAlbums()
  albums.value = albumsStore.albums
}

const viewAlbum = (id) => {
  router.push(`/albums/${id}`)
}

onMounted(fetchAlbums)
</script>

<style>
.album-table {
  width: 50%;
  border-collapse: collapse;
  border-spacing: 0 10px;
  margin:0 auto;
}

.album-item {
  transition: background-color 0.3s, color 0.3s;
}

.album-item:hover {
  background-color: #ffffff;
  color: pink;
}

.album-id, .album-title {
  padding: 10px;
  border: 1px solid pink;
}

.album-id {
  font-weight: bold;
}

.album-title {
  font-family: 'Arial', sans-serif; 
}
</style>
