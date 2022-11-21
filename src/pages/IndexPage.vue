<template>
  <q-page class="row items-center justify-evenly">
    <q-list style="min-width: 480px">
      <q-item clickable v-ripple>
        <q-item-section>text</q-item-section>
        <q-item-section>{{ t('text') }}</q-item-section>
      </q-item>
      <q-item clickable v-ripple>
        <q-item-section>interpolate Object</q-item-section>
        <q-item-section>{{ t('interpolateObj', nameA) }}</q-item-section>
      </q-item>
      <q-item clickable v-ripple>
        <q-item-section>interpolate Array</q-item-section>
        <q-item-section>{{ t('interpolateArr', nameB) }}</q-item-section>
      </q-item>
      <q-item clickable v-ripple>
        <q-item-section>Single</q-item-section>
        <q-item-section>{{ t('plural', 1) }}</q-item-section>
      </q-item>
      <q-item clickable v-ripple>
        <q-item-section>Plural</q-item-section>
        <q-item-section>{{ t('plural', { n: number }) }}</q-item-section>
      </q-item>
      <q-item clickable v-ripple>
        <q-item-section>Number</q-item-section>
        <q-item-section>{{ n(number) }}</q-item-section>
      </q-item>
      <q-item clickable v-ripple>
        <q-item-section>Date</q-item-section>
        <q-item-section>{{ d(date) }}</q-item-section>
      </q-item>
    </q-list>
  </q-page>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import { useI18n } from 'vue-i18n';

const { t, n, d } = useI18n();
const nameA = ref({ name: 'Tobias', surname: 'Mesquita' });
const nameB = ref(['Tobias', 'Mesquita']);
const number = ref(1234);
const date = ref(new Date());
</script>
