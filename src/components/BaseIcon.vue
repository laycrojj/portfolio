   
  <script setup lang="ts">

import { computed, type Component } from 'vue';
import DefaultOwenIcon from './icons/DefaultOwenIcon.vue';
import IconOwenBeret from './icons/IconOwenBeret.vue';
import IconOwenHoodie from './icons/IconOwenHoodie.vue';
import IconOwenMortarBoard from './icons/IconOwenMortarBoard.vue';


  const icons: Record<string, Component> = {
    "Developer": IconOwenHoodie,
    "3D Artist": IconOwenBeret,
    "Dad":DefaultOwenIcon,
    "Post Graduate":IconOwenMortarBoard,
    // ...
    }
   
   const props = defineProps({
        name: {
            type: String,
            required: true,
        },
    });
   
    const iconComponent = computed(() => 
    {
        return icons[props.name] ?? DefaultOwenIcon
    });

  </script>
  
  <template>
      <component
        :is="iconComponent"
        role="img"
        :aria-label="`Sketch of Owen as ${name}`"
        class="inline-block fill-current"
      />
    </template>