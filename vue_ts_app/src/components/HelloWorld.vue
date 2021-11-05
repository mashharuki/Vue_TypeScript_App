<template>
    <h1 class="bg-info text-white p-2">{{ msg }}</h1>
    <div class="container">
      <h2 class="my-3"> 
        number counter.
      </h2>
      <div class="alert alert-info">
        <h3 v-on:click="doAction">
          {{val}} count.
        </h3>
      </div>
    </div>
</template>

<script lang="tsx">
  import { VNode } from 'vue'
  import { VueC } from "vue-class-component"

  export default class HelloWorld extends VueC {
    
    msg = "Vue sample."
    val = 1

    doAction(): void {
      this.val += 1
    }

    get sum(): number {
      let re = 0
      for (let i=1;i<this.val;i++) {
        re += 1
      }
      return re
    }

    render(): VNode {
      return (
        <div>
          <h1 class="bg-info text-white p-2">{this.msg}</h1>
          <div class="container">
            <h2 class="my-3">number counter.</h2>
            <div class="alert alert-info">
              <h3 onClick={this.doAction}>{this.val}</h3>
              <h4>(sum: {this.sum})</h4>
            </div>
          </div>
        </div>
      )
    }
  }
</script>