<script setup lang="ts">
import { Proxy } from '~/composables/image'
const size = ref(useStorage('size', 150))
function LargeSize() {
  size.value && (size.value += 20)
}
function RestSize() {
  size.value && (size.value = 150)
}
</script>

<template>
  <RouterLink to="/" btn m-3>
    Back
  </RouterLink>
  <RouterLink to="/bar" btn m-3>
    Bar
  </RouterLink>
  <button btn m-3 @click="LargeSize">
    Large
  </button>
  <button btn m-3 @click="RestSize">
    Rest
  </button>
  <div flex="~ col  sm:row" items-center>
    <Proxy :style="{ width: `${size}px`, height: `${size}px` }" rounded-full w-100 h-100 />
    <p flex-1>
      Hojas de Estilo en Cascada (del inglés Cascading Style Sheets) o CSS es el lenguaje de estilos utilizado para describir la presentación de documentos HTML o XML (en-US) (incluyendo varios lenguajes basados en XML como SVG, MathML o XHTML). CSS describe como debe ser renderizado el elemento estructurado en la pantalla, en papel, en el habla o en otros medios.CSS es uno de los lenguajes base de la Open Web y posee una especificación estandarizada por parte del W3C. Anteriormente , el desarrollo de varias partes de las especificaciones de CSS era realizado de manera sincrónica, lo que permitía el versionado de las recomendaciones. Probablemente habrás escuchado acerca de CSS1, CSS2.1, CSS3. Sin embargo, CSS4 nunca se ha lanzado como una versión oficial.
      Desde CSS3, el alcance de las especificaciones se incrementó de forma significativa y el progreso de los diferentes módulos de CSS comenzó a mostrar varias diferencias, lo que hizo más efectivo desarrollar y publicar recomendaciones separadas por módulos. En vez de versionar las especificaciones de CSS, la W3C actualmente realiza una captura de las ultimas espcificaciones estables de CSS
    </p>
  </div>
</template>
