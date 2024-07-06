import { NuxtPage } from '#build/components';
<template>
  <div>
    <ClientOnly>
      <Nav />
      <NuxtPage />
      <Footer />
    </ClientOnly>
  </div>
</template>
