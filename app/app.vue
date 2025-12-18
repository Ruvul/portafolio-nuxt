<script setup>
useHead({
  meta: [
    { name: 'viewport', content: 'width=device-width, initial-scale=1' }
  ],
  link: [
    { rel: 'icon', href: '/favicon.ico' }
  ],
  htmlAttrs: {
    lang: 'es'
  }
})

const title = 'IURDSYS DEV MX - Portafolio Comunitario'
const description = 'Portafolio comunitario del equipo de desarrollo IURDSYS DEV MX. Un espacio colaborativo donde cada desarrollador comparte su trabajo y experiencia.'

useSeoMeta({
  title,
  description,
  ogTitle: title,
  ogDescription: description,
  twitterCard: 'summary_large_image'
})
</script>

<template>
  <UApp>
    <UHeader>
      <template #left>
        <NuxtLink to="/" class="flex items-center gap-3">
          <AppLogo />
        </NuxtLink>
      </template>

      <template #center>
        <nav class="hidden md:flex items-center gap-6">
          <UButton
            to="/"
            label="Home"
            color="neutral"
            variant="ghost"
          />
        </nav>
      </template>

      <template #right>
        <UColorModeButton />
      </template>
    </UHeader>

    <UMain>
      <NuxtPage />
    </UMain>

    <UFooter>
      <template #left>
        <p class="text-sm text-muted">
          IURDSYS DEV MX © {{ new Date().getFullYear() }}
        </p>
      </template>

      <template #right>
        <p class="text-sm text-muted">
          Portafolio Comunitario
        </p>
      </template>
    </UFooter>
  </UApp>
</template>
