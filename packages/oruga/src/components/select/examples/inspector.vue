<script setup lang="ts">
import type { InspectData } from "@docs";
import type { SelectClasses, SelectProps } from "../props";

const inspectData: InspectData<
    SelectClasses,
    SelectProps<unknown, true | false> & {
        fieldvariant: string;
        fieldmessage: string;
    }
> = {
    rootClass: {
        class: "rootClass",
        description: "Class of the root element.",
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
            data.fieldvariant = "info";
            data.fieldmessage = "Info for this field";
        },
    },
    expandedClass: {
        class: "expandedClass",
        description: "Class of the root element when expanded.",
        properties: ["expanded"],
        action: (data): void => {
            data.expanded = true;
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
    hasIconRightClass: {
        class: "hasIconRightClass",
        description: "Class to the root element when a right icon is used.",
        properties: ["iconRight"],
        action: (data): void => {
            data.iconRight = "times-circle";
        },
    },
    multipleClass: {
        class: "multipleClass",
        description: "Class of the root element when multiple.",
        properties: ["multiple"],
        action: (data): void => {
            data.multiple = true;
        },
    },
    selectClass: {
        class: "selectClass",
        description: "Class of the native select element.",
    },
    placeholderClass: {
        class: "placeholderClass",
        description: "Class of the native select element with a placeholder.",
    },
    arrowedClass: {
        class: "arrowedClass",
        description: "Class of the native select element with an arrow.",
        info: "It applies the arrow icon using background-image and background-position on select element. An alternative to override this is the iconRight prop (globally or not).",
    },
    iconLeftSpaceClass: {
        class: "iconLeftSpaceClass",
        description: "Class of the native select element with left icon space.",
        properties: ["icon"],
        action: (data): void => {
            data.icon = "envelope";
        },
    },
    iconRightSpaceClass: {
        class: "iconRightSpaceClass",
        description:
            "Class of the native select element with right icon space.",
        properties: ["iconRight"],
        action: (data): void => {
            data.iconRight = "times-circle";
        },
    },
    iconLeftClass: {
        class: "iconLeftClass",
        description: "Class of the left icon element.",
        properties: ["icon"],
        action: (data): void => {
            data.icon = "envelope";
        },
    },
    iconRightClass: {
        class: "iconRightClass",
        description: "Class of the right icon element.",
        properties: ["iconRight"],
        action: (data): void => {
            data.iconRight = "times-circle";
        },
    },
};
</script>

<template>
    <inspector-wrapper v-slot="props" :inspect-data="inspectData">
        <o-field :variant="props.fieldvariant" :message="props.fieldmessage">
            <o-select
                v-bind="props"
                placeholder="Select a character"
                aria-label="Select a character">
                <optgroup label="Black Sails">
                    <option value="flint">Flint</option>
                    <option value="silver">Silver</option>
                    <option value="vane">Vane</option>
                    <option value="billy">Billy</option>
                    <option value="jack">Jack</option>
                </optgroup>
                <optgroup label="Breaking Bad">
                    <option value="heisenberg">Heisenberg</option>
                    <option value="jesse">Jesse</option>
                    <option value="saul">Saul</option>
                    <option value="mike">Mike</option>
                </optgroup>
            </o-select>
        </o-field>
    </inspector-wrapper>
</template>
