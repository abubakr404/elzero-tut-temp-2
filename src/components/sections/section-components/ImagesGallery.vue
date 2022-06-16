<template>
  <div class="box">
    <slot></slot>
    <div class="caption">
      <h4><slot name="work-title"></slot></h4>
      <p><slot name="work-category"></slot></p>
    </div>
  </div>
</template>
