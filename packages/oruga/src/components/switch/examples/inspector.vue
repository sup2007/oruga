<script setup lang="ts">
import type { InspectData } from "@docs";
import type { SwitchClasses, SwitchProps } from "../props";

const inspectData: InspectData<SwitchClasses, SwitchProps<unknown>> = {
    rootClass: {
        class: "rootClass",
        description: "Class of the root element.",
    },
    checkedClass: {
        class: "checkedClass",
        description: "Class of the root element when checked.",
        properties: ["modelValue"],
        action: (data): void => {
            data.modelValue = true;
        },
    },
    sizeClass: {
        class: "sizeClass",
        description: "Class of the root element with size.",
        properties: ["size"],
        suffixes: ["small", "medium", "large"],
        action: (data): void => {
            data.size = "large";
        },
    },
    variantClass: {
        class: "variantClass",
        description: "Class of the root element with variant.",
        properties: ["variant"],
        suffixes: ["primary", "info", "warning", "danger"],
        action: (data): void => {
            data.variant = "warning";
            data.modelValue = true;
        },
    },
    passiveVariantClass: {
        class: "passiveVariantClass",
        description: "Class of the root element with passive variant.",
        properties: ["passiveVariant"],
        suffixes: ["primary", "info", "warning", "danger"],
        action: (data): void => {
            data.passiveVariant = "danger";
            data.modelValue = false;
        },
    },
    positionClass: {
        class: "positionClass",
        description: "Class of the root element with position.",
        properties: ["position"],
        action: (data): void => {
            data.position = "left";
        },
    },
    disabledClass: {
        class: "disabledClass",
        description: "Class of the root element when disabled.",
        properties: ["disabled"],
        action: (data): void => {
            data.disabled = true;
        },
    },
    roundedClass: {
        class: "roundedClass",
        description: "Class of the root element when rounded.",
        properties: ["rounded"],
        action: (data): void => {
            data.rounded = true;
        },
    },
    inputClass: {
        class: "inputClass",
        description: "Class of the native input element.",
    },
    labelClass: {
        class: "labelClass",
        description: "Class of the switch label element.",
    },
};
</script>

<template>
    <inspector-wrapper v-slot="props" :inspect-data="inspectData">
        <o-switch v-bind="props">Switch</o-switch>
    </inspector-wrapper>
</template>
