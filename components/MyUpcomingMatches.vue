<script lang="ts" setup>
import SimpleMatchDisplay from "./SimpleMatchDisplay.vue";
</script>

<template>
  <div class="flex gap-4 overflow-x-auto">
    <template v-if="matches?.length > 0">
      <SimpleMatchDisplay
        :key="match.id"
        :match="match"
        v-for="match of matches"
      ></SimpleMatchDisplay>
    </template>
    <template v-else>
      <div class="text-center w-full p-4">
        <p class="text-muted-foreground">
          You don't have any upcoming matches.
        </p>
      </div>
    </template>
  </div>
</template>

<script lang="ts">
export default {
  computed: {
    matches() {
      return useMatchLobbyStore().upcomingMatches;
    },
  },
};
</script>
