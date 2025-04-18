---
sidebarDepth: 2
---

# Slider

<section class="odocs-head">

The **Slider** input component let user select a value or range from a given range with a graphic slider.
The component implements the W3C ARIA APG [Slider Pattern](https://www.w3.org/WAI/ARIA/apg/patterns/slider/).
Use it with the [Field](/components/Field) component to access all the functionalities.

</section>

<section class="odocs-examples">

## Examples

<example-slider />

</section>

<section class="odocs-specs">

## Slider component

> A slider to select a value or range from a given range.

```html
<o-slider></o-slider>
```

### Props

| Prop name         | Description                                                           | Type                           | Values                                                                          | Default                                                                                                                                                    |
| ----------------- | --------------------------------------------------------------------- | ------------------------------ | ------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------- |
| ariaLabel         | Accessibility aria-label to to be passed to the slider thumb element. | string                         | -                                                                               | <div><small>From <b>config</b>:</small></div><code style='white-space: nowrap; padding: 0;'>slider: {<br>&nbsp;&nbsp;ariaLabel: undefined<br>}</code>      |
| biggerSliderFocus | Increases slider size on focus                                        | boolean                        | -                                                                               | <code style='white-space: nowrap; padding: 0;'>false</code>                                                                                                |
| disabled          | Slider will be disabled                                               | boolean                        | -                                                                               | <code style='white-space: nowrap; padding: 0;'>false</code>                                                                                                |
| format            | Define v-model format                                                 | "percent" \| "raw"             | `row`, `percent`                                                                | <div><small>From <b>config</b>:</small></div><code style='white-space: nowrap; padding: 0;'>slider: {<br>&nbsp;&nbsp;format: "raw"<br>}</code>             |
| formatter         | Function to format the tooltip label for display                      | ((value: number) =&gt; string) | -                                                                               |                                                                                                                                                            |
| indicator         | Show indicators                                                       | boolean                        | -                                                                               | <code style='white-space: nowrap; padding: 0;'>false</code>                                                                                                |
| lazy              | Update v-model only when dragging is finished                         | boolean                        | -                                                                               | <code style='white-space: nowrap; padding: 0;'>false</code>                                                                                                |
| locale            | Date format locale                                                    | string \| string[]             | -                                                                               | <div><small>From <b>config</b>:</small></div><code style='white-space: nowrap; padding: 0;'>{<br>&nbsp;&nbsp;locale: undefined<br>}</code>                 |
| max               | Maximum value                                                         | number                         | -                                                                               | <code style='white-space: nowrap; padding: 0;'>100</code>                                                                                                  |
| min               | Minimum value                                                         | number                         | -                                                                               | <code style='white-space: nowrap; padding: 0;'>0</code>                                                                                                    |
| v-model           | The input value state                                                 | [number, number] \| number     | -                                                                               |                                                                                                                                                            |
| override          | Override existing theme classes completely                            | boolean                        | -                                                                               |                                                                                                                                                            |
| range             | Enable range slider                                                   | boolean                        | -                                                                               | <code style='white-space: nowrap; padding: 0;'></code>                                                                                                     |
| rounded           | Rounded thumb                                                         | boolean                        | -                                                                               | <div><small>From <b>config</b>:</small></div><code style='white-space: nowrap; padding: 0;'>slider: {<br>&nbsp;&nbsp;rounded: false<br>}</code>            |
| size              | Vertical size of slider                                               | string                         | `small`, `medium`, `large`                                                      | <div><small>From <b>config</b>:</small></div><code style='white-space: nowrap; padding: 0;'>slider: {<br>&nbsp;&nbsp;size: undefined<br>}</code>           |
| step              | Step interval of ticks                                                | number                         | -                                                                               | <code style='white-space: nowrap; padding: 0;'>1</code>                                                                                                    |
| ticks             | Show tick marks                                                       | boolean                        | -                                                                               | <code style='white-space: nowrap; padding: 0;'>false</code>                                                                                                |
| tooltip           | Show tooltip when thumb is being dragged                              | boolean                        | -                                                                               | <div><small>From <b>config</b>:</small></div><code style='white-space: nowrap; padding: 0;'>slider: {<br>&nbsp;&nbsp;tooltip: true<br>}</code>             |
| tooltipAlways     | Tooltip displays always                                               | boolean                        | -                                                                               | <code style='white-space: nowrap; padding: 0;'>false</code>                                                                                                |
| tooltipVariant    | Color of the tooltip                                                  | string                         | `primary`, `info`, `success`, `warning`, `danger`, `and any other custom color` | <div><small>From <b>config</b>:</small></div><code style='white-space: nowrap; padding: 0;'>slider: {<br>&nbsp;&nbsp;tooltipVariant: undefined<br>}</code> |
| variant           | Color of the slider                                                   | string                         | `primary`, `info`, `success`, `warning`, `danger`, `and any other custom color` | <div><small>From <b>config</b>:</small></div><code style='white-space: nowrap; padding: 0;'>slider: {<br>&nbsp;&nbsp;variant: undefined<br>}</code>        |

### Events

| Event name         | Properties                                               | Description                     |
| ------------------ | -------------------------------------------------------- | ------------------------------- |
| update:model-value | **value** `number \| number[]` - updated modelValue prop | modelValue prop two-way binding |
| change             | **value** `number \| number[]` - updated modelValue prop | on value change event           |
| dragging           | **value** `number \| number[]` - updated modelValue prop | on dragging event               |
| dragstart          |                                                          | on drag start event             |
| dragend            |                                                          | on drag end event               |

### Slots

| Name    | Description                         | Bindings |
| ------- | ----------------------------------- | -------- |
| default | Define additional slider ticks here |          |

</section>

<section class="odocs-specs">

## SliderTick component

```html
<o-slider-tick></o-slider-tick>
```

### Props

| Prop name | Description                                | Type             | Values | Default                                                |
| --------- | ------------------------------------------ | ---------------- | ------ | ------------------------------------------------------ |
| label     | Tick label                                 | number \| string | -      |                                                        |
| override  | Override existing theme classes completely | boolean          | -      |                                                        |
| value     | Value of single tick                       | number           | -      | <code style='white-space: nowrap; padding: 0;'></code> |

### Slots

| Name    | Description                                  | Bindings |
| ------- | -------------------------------------------- | -------- |
| default | Override tick content, default is label prop |          |

</section>

<section class="odocs-classes">

## Class Inspector

<inspector-slider-viewer />

</section>

<section class="odocs-style">

## Sass variables

<div class="theme-oruga">

> Current theme ➜ _[Oruga](https://github.com/oruga-ui/theme-oruga)_

| SASS Variable                 | Default                                      |
| ----------------------------- | -------------------------------------------- |
| $slider-background            | transparent                                  |
| $slider-margin                | 1em 0                                        |
| $slider-mark-size             | 0.75rem                                      |
| $slider-font-size             | var(--#{$prefix}base-font-size)              |
| $slider-rounded-borded-radius | var( --#{$prefix}base-border-radius-rounded) |
| $slider-thumb-background      | var(--#{$prefix}white)                       |
| $slider-thumb-border          | 1px solid var(--#{$prefix}grey-light)        |
| $slider-thumb-radius          | var(--#{$prefix}base-border-radius)          |
| $slider-thumb-shadow          | none                                         |
| $slider-thumb-to-track-ratio  | 2                                            |
| $slider-thumb-transform       | scale(1.25)                                  |
| $slider-tick-background       | var(--#{$prefix}primary)                     |
| $slider-tick-radius           | var(--#{$prefix}base-border-radius)          |
| $slider-tick-to-track-ratio   | 0.5                                          |
| $slider-tick-width            | 3px                                          |
| $slider-track-background      | var(--#{$prefix}grey-lighter)                |
| $slider-fill-background       | var(--#{$prefix}primary)                     |
| $slider-track-border-radius   | var(--#{$prefix}base-border-radius)          |
| $slider-track-border          | 0px solid var(--#{$prefix}grey)              |
| $slider-track-disabled        | 0.5                                          |
| $slider-track-radius          | var(--#{$prefix}base-border-radius)          |
| $slider-track-shadow          | 0px 0px 0px var(--#{$prefix}grey)            |

See ➜ 📄 [Full scss file](https://github.com/oruga-ui/theme-oruga/tree/main/src/assets/scss/components/_slider.scss)

</div>
<div class="theme-bulma">

> Current theme ➜ _[Bulma](https://github.com/oruga-ui/theme-bulma)_

| SASS Variable                | Default                            |
| ---------------------------- | ---------------------------------- |
| $slider-tick-label-size      | 0.75rem                            |
| $slider-thumb-shadow         | none                               |
| $slider-thumb-to-track-ratio | 2                                  |
| $slider-tick-to-track-ratio  | 0.5                                |
| $slider-tick-width           | 3px                                |
| $slider-colors               | dv.$colors                         |
| $slider-radius               | css.getVar("radius")               |
| $slider-background           | css.getVar("grey-lighter")         |
| $slider-color                | css.getVar("primary")              |
| $slider-track-border         | 0px solid css.getVar("grey")       |
| $slider-track-shadow         | 0px 0px 0px css.getVar("grey")     |
| $slider-thumb-background     | css.getVar("scheme-main")          |
| $slider-thumb-radius         | css.getVar("radius")               |
| $slider-thumb-border         | 1px solid css.getVar("grey-light") |
| $slider-tick-radius          | css.getVar("radius")               |
| $slider-tick-background      | css.getVar("grey-light")           |

See ➜ 📄 [Full scss file](https://github.com/oruga-ui/theme-bulma/tree/main/src/assets/scss/components/_slider.scss)

</div>
<div class="theme-bootstrap">

> Current theme ➜ _[Bootstrap](https://github.com/oruga-ui/theme-bootstrap)_

| SASS Variable       | Default               |
| ------------------- | --------------------- |
| $slider-tick-width  | 0.25rem               |
| $slider-tick-height | 0.25rem               |
| $slider-tick-radius | 50%                   |
| $slider-tick-bg     | var(--#{$prefix}gray) |

See ➜ 📄 [Full scss file](https://github.com/oruga-ui/theme-bootstrap/tree/main/src/assets/scss/components/_slider.scss)

</div>

</section>
