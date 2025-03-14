<script setup lang="ts">
import { reactive } from 'vue';
import { TheChessboard } from 'vue3-chessboard';
import 'vue3-chessboard/style.css';
import type { BoardApi, BoardConfig } from 'vue3-chessboard';

let boardAPI: BoardApi;

const boardConfig: BoardConfig = reactive({
  coordinates: true,
  orientation: 'white',
  position: 'start',
});

function onBoardCreated(api: BoardApi) {
  boardAPI = api;
}
</script>

<template>
  <h2>CheckM8</h2>

  <!-- Plateau -->
  <TheChessboard
    :board-config="boardConfig"
    reactive-config
    @board-created="onBoardCreated">
  </TheChessboard>
</template>

<style scoped>
</style>
