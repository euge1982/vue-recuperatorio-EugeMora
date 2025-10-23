# vue-recuperatorio-EugeMora

Enunciado del Ejercicio: Días de la Semana Interactivos
El alumno deberá crear una aplicación Vue.js 3 Composition API (con <script setup>) y TypeScript, utilizando tres componentes, para visualizar e interactuar con los días de la semana.

1. Modelo de Datos y Estructura
Modelo TypeScript: Cree la interfaz IWeekDay en un archivo src/models/WeekDay.ts. Esta interfaz debe contener:

id: number (Para usar en la clave de v-for).

name: string (El nombre del día, ej: "Lunes").

selected: boolean (Indica si el día está seleccionado/activo).

Estructura de Componentes:

App.vue (Raíz).

DayManager.vue (Padre): Contiene el array de días (IWeekDay[]), los botones de control y la lógica de selección.

DayCard.vue (Hijo): Renderiza cada día individualmente.

2. Flujo de Datos y Reactividad
Datos en el Padre: El array de objetos (IWeekDay[]) debe ser declarado en DayManager.vue utilizando ref() y tipado estricto (Ref<IWeekDay[]>()). Inicialmente, ningún día debe estar seleccionado (selected: false).

Comunicación Padre → Hijo (Props): DayManager.vue debe usar la directiva v-for para pasar cada objeto individual de IWeekDay a una instancia de DayCard.vue como una prop tipada.

3. Funcionalidad del Componente Padre (DayManager.vue)
Renderizado de Controles (v-for): DayManager.vue debe generar un botón por cada día de la semana utilizando la directiva v-for sobre el array de días.

Lógica de Selección: Al hacer clic en un botón, debe ejecutarse una función que:

Reciba el id o el name del día presionado.

Actualice el array: Marque el día correspondiente como selected: true.

Asegure la exclusividad: Todos los demás días deben ser marcados como selected: false.

Comunicación con el Hijo: El array (ref) actualizado debe reflejarse automáticamente en las props de los componentes hijos.

4. Funcionalidad del Componente Hijo (DayCard.vue)
Recepción de Datos (Props): DayCard.vue debe definir y tipar la prop que recibe el objeto IWeekDay.

Renderizado (v-bind:class): La tarjeta debe usar v-bind:class para aplicar estilos de Tailwind de forma condicional, basándose en el estado de la propiedad selected que recibe:

Estado normal: Fondo claro y borde simple.

Estado selected: true: Cambiar el fondo a un color fuerte (ej. azul) y el texto a blanco para indicar que ese es el día activo.

Requisitos Mínimos para Aprobar:
Tipado Estricto (TS): Correcta definición de la interface y uso de tipado en ref() y props.

Componentes: Creación e importación correcta de los tres componentes.

v-for: Uso funcional para generar los botones en el padre y las tarjetas en el hijo (o la lista de tarjetas en el padre).

v-bind:class: Uso correcto en DayCard.vue para estilizar la tarjeta según el estado selected.

Flujo de Datos: La acción del botón en el padre debe modificar el array, y ese cambio debe reflejarse en el estilo del componente hijo correspondiente.

Exclusividad: Solo un día puede estar selected: true a la vez.

Forma de entrega: Link de respositorio de GitHub.
```
