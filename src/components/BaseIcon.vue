   
  <script setup lang="ts">

import { computed } from 'vue';
import DefaultOwenIcon from './icons/DefaultOwenIcon.vue';
import IconOwenBeret from './icons/IconOwenBeret.vue';
import IconOwenHoodie from './icons/IconOwenHoodie.vue';
import IconOwenMortarBoard from './icons/IconOwenMortarBoard.vue';


  const icons = {
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
        return icons[props.name]
    });

  </script>
  
  <template>
      <component
        :is="iconComponent"
        role="img"
        class="inline-block fill-current"
      />
    </template>