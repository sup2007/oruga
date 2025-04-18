<script setup lang="ts">
import { ref } from "vue";
import { useOruga } from "@oruga-ui/oruga-next";
import type { TableColumn } from "@oruga-ui/oruga-next";

const oruga = useOruga();

const columns: TableColumn[] = [
    {
        field: "id",
        label: "ID",
        width: "40",
        numeric: true,
    },
    {
        field: "first_name",
        label: "First Name",
    },
    {
        field: "last_name",
        label: "Last Name",
    },
    {
        field: "date",
        label: "Date",
        position: "centered",
    },
    {
        field: "gender",
        label: "Gender",
    },
];

const data = [
    {
        id: 1,
        first_name: "Jesse",
        last_name: "Simmons",
        date: "2016-10-15 13:43:27",
        gender: "Male",
    },
    {
        id: 2,
        first_name: "John",
        last_name: "Jacobs",
        date: "2016-12-15 06:00:53",
        gender: "Male",
    },
    {
        id: 3,
        first_name: "Tina",
        last_name: "Gilbert",
        date: "2016-04-26 06:26:28",
        gender: "Female",
    },
    {
        id: 4,
        first_name: "Clarence",
        last_name: "Flores",
        date: "2016-04-10 10:28:46",
        gender: "Male",
    },
    {
        id: 5,
        first_name: "Anne",
        last_name: "Lee",
        date: "2016-12-06 14:38:38",
        gender: "Female",
    },
];

const draggingRow = ref<any>();
const draggingRowIndex = ref<number>(0);
const draggingColumn = ref<TableColumn>();
const draggingColumnIndex = ref<number>(0);

function dragstart(row, index, event): void {
    draggingRow.value = row;
    draggingRowIndex.value = index;
    event.dataTransfer.effectAllowed = "copy";
}

function dragover(row, index, event): void {
    event.preventDefault();
    event.dataTransfer.dropEffect = "copy";
    event.target.closest("tr").classList.add("is-selected");
}

function dragleave(row, index, event): void {
    event.preventDefault();
    event.target.closest("tr").classList.remove("is-selected");
}

function drop(row, index, event): void {
    event.target.closest("tr").classList.remove("is-selected");
    const droppedOnRowIndex = index;
    oruga.notification.open(
        `Moved ${draggingRow.value?.first_name} from row ${
            draggingRowIndex.value + 1
        } to ${droppedOnRowIndex + 1}`,
    );
}

function columndragstart(column, index, event): void {
    draggingColumn.value = column;
    draggingColumnIndex.value = index;
    event.dataTransfer.effectAllowed = "copy";
}

function columndragover(column, index, event): void {
    event.preventDefault();
    event.dataTransfer.dropEffect = "copy";
    event.target.closest("th").classList.add("is-selected");
}

function columndragleave(column, index, event): void {
    event.preventDefault();
    event.target.closest("th").classList.remove("is-selected");
}

function columndrop(column, index, event): void {
    event.target.closest("th").classList.remove("is-selected");
    const droppedOnColumnIndex = index;
    oruga.notification.open(
        `Moved ${draggingColumn.value?.field} from column ${
            draggingColumnIndex.value + 1
        } to ${droppedOnColumnIndex + 1}`,
    );
}
</script>

<template>
    <section>
        <o-table
            :data="data"
            :columns="columns"
            draggable
            draggable-column
            @dragstart="dragstart"
            @drop="drop"
            @dragover="dragover"
            @dragleave="dragleave"
            @columndragstart="columndragstart"
            @columndrop="columndrop"
            @columndragover="columndragover"
            @columndragleave="columndragleave" />
    </section>
</template>

<style scoped>
:deep(.is-selected) {
    background-color: lightblue;
}
</style>
