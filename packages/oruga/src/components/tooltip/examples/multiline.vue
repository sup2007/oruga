<template>
    <section class="odocs-spaced">
        <p>
            <o-tooltip
                label="Tooltip multiline, probably because it's too long for a casual tooltip"
                multiline>
                <o-button label="Multiline" />
            </o-tooltip>

            <o-tooltip label="It's not brief, but it's also not long" multiline>
                <o-button label="Multiline (small)" />
            </o-tooltip>

            <o-tooltip
                label="Tooltip large multiline, because it's too long to be on a medium size. Did I tell you it's really long? Yes, it is — I assure you!"
                position="bottom"
                multiline>
                <o-button label="Multiline (large)" />
            </o-tooltip>
        </p>
    </section>
</template>
