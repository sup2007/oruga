<script setup lang="ts">
import type { PropType } from "vue";

import OPagination from "@/components/pagination/Pagination.vue";

import type { ComponentClass } from "@/types";

defineOptions({
    isOruga: true,
    name: "OTablePagination",
    configField: "table",
    inheritAttrs: false,
});

defineProps({
    current: { type: Number, default: undefined },
    paginated: { type: Boolean, default: false },
    rootClass: {
        type: [String, Array, Object] as PropType<ComponentClass>,
        default: undefined,
    },
});

const emits = defineEmits<{
    /**
     * current prop two-way binding
     * @param value {number} updated current prop
     */
    "update:current": [value: number];
    /**
     * on current change event
     * @param value {number} current value
     */
    change: [event: number];
}>();

const currentPage = defineModel<number>("current");

/** paginator change listener */
function pageChanged(page: number): void {
    const newPage = page > 0 ? page : 1;
    currentPage.value = newPage;
    emits("change", newPage);
}
</script>

<template>
    <div :class="rootClass">
        <div>
            <slot />
        </div>

        <div>
            <o-pagination
                v-if="paginated"
                v-bind="$attrs"
                :current="currentPage"
                @change="pageChanged" />
        </div>
    </div>
</template>
