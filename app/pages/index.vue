<template>
  <div>
    <!-- Hero Section -->
    <UPageHero
      title="IURDSYS DEV MX"
      description="Portafolio Comunitario del Equipo de Desarrollo"
      :ui="{
        title: 'text-5xl sm:text-6xl font-bold',
        description: 'text-xl mt-6'
      }"
    />

    <!-- Instructions Section -->
    <UPageSection
      id="instrucciones"
      title="Cómo Contribuir al Portafolio"
      description="Sigue estos pasos para añadir tu página personal al portafolio comunitario"
      class="bg-background/50"
    >
      <UPageColumns>
        <div class="space-y-6">
          <div
            v-for="(step, index) in steps"
            :key="index"
            class="flex gap-4"
          >
            <div class="flex-shrink-0">
              <div class="flex items-center justify-center w-10 h-10 rounded-full bg-primary text-primary-contrast font-bold">
                {{ index + 1 }}
              </div>
            </div>
            <div class="flex-1">
              <h3 class="text-lg font-semibold mb-2">
                {{ step.title }}
              </h3>
              <p class="text-muted">
                {{ step.description }}
              </p>
            </div>
          </div>
        </div>
      </UPageColumns>
    </UPageSection>

    <!-- Team Members Section -->
    <UPageSection
      id="equipo"
      title="Nuestro Equipo"
      description="Desarrolladores que conforman IURDSYS DEV MX"
    >
      <UPageColumns>
        <UPageCard
          title="Añade tu Perfil"
          description="Sigue las instrucciones anteriores para añadir tu propia página al portafolio comunitario."
          icon="i-lucide-user-plus"
          :ui="{
            body: 'flex flex-col items-center text-center'
          }"
        />
      </UPageColumns>
    </UPageSection>

    <!-- Call to Action -->
    <UPageSection>
      <UPageCTA
        title="¿Listo para contribuir?"
        description="Clona el repositorio y añade tu página personal siguiendo los pasos descritos arriba."
        variant="subtle"
        :links="[{
          label: 'Ver Instrucciones',
          to: '#instrucciones',
          trailingIcon: 'i-lucide-arrow-down',
          color: 'primary'
        }]"
      />
    </UPageSection>
  </div>
</template>

<script setup lang="ts">
const steps = [
  {
    title: 'Descargar el repositorio en local',
    description: 'Clona el repositorio del portafolio comunitario en tu máquina local usando Git.'
  },
  {
    title: 'Añadir los cambios correspondientes',
    description: 'Crea tu página personal en el directorio pages/ y añade tus componentes personalizados si es necesario.'
  },
  {
    title: 'Realizar el commit al repositorio remoto',
    description: 'Haz commit de tus cambios y súbelos al repositorio remoto mediante un pull request.'
  },
  {
    title: 'Esperar a que el flujo de CI/CD complete el despliegue',
    description: 'Una vez aprobado tu pull request, el pipeline de CI/CD desplegará automáticamente los cambios.'
  }
]
</script>
