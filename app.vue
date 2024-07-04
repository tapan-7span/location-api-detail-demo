import { NuxtPage } from '#build/components';
<template>
  <div>
    <ClientOnly>
      <Nav />
      <NuxtPage />
    </ClientOnly>
  </div>
</template>
