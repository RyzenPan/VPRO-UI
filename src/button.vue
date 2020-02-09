<template>
  <button class="v-button" :class="{[`icon-${iconPosition}`]:iconPosition}" @click="$emit('click')">
    <v-icon class="icons" v-if="icon && !loading" :name="icon"></v-icon>
    <v-icon class="icons loading" v-if="loading" name="loading"></v-icon>
    <div class="content">
      <slot></slot>
    </div>
  </button>
</template>

<script>
export default {
  props: {
    icon: {},
    iconPosition: {
      type:String,
      default:"left",
      validator(val){
        if(val !== "left" && val !== "right"){
          return false
        } else {
          return true
        }
      }
    },
    loading:{
      type:Boolean,
      default:false
    }
  }
}
</script>

<style lang="less">
@keyframes spin{
  0% { 
    transform: rotate(0deg)
   }
  100% { 
    transform: rotate(360deg)
   }
}
.v-button {
  font-size: var(--font-size);
  height: var(--button-height);
  padding: 0 1em;
  border-radius: 4px;
  border: 1px solid var(--border-color);
  background: var(--button-bg);
  display: inline-flex;
  vertical-align: -webkit-baseline-middle;
  justify-content: center;
  align-items: center;
  &:hover {
    border-color: var(--border-color-hover);
  }
  &:active {
    background-color: var(--button-active-bg);
  }
  &:focus {
    outline: none;
  }
  .icons {
    order: 1;
  }
  .content {
    order:2;
  }

  
  &.icon-right {
     >.content {
      order: 1;
    }
     >.icons {
       margin:0;
       margin-left: 0.4em;
      order:2;
    }
  }
}

.loading {
 animation: spin 1.5s infinite linear;
}
</style>