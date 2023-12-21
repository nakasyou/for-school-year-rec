<script lang="ts">
  import type { Point } from '../types'

  export let onChange: (point: Point) => void

  let a = ""
  let b = ""
  let c = ""

  let point: Point = {
    a: 0, b: 0, c: 0
  }
  
  const changeHandler = () => {
    const map = [0, 5, 3, 1]

    point.a = map[parseInt(a)]
    point.b = map[parseInt(b)]
    point.c = map[parseInt(c)]

    onChange(point)
  }
</script>
<div>
  <div class="text-xl">競技2 | 王様は誰だ!? 王様ドッヂボール</div>
  <div class="pl-1">
    <div class="grid grid-cols-2 pl-1">
      <div>A</div>
      <div>
        <select bind:value={a} on:change={changeHandler}>
          <option value="1">1位</option>
          <option value="2">2位</option>
          <option value="3">3位</option>
        </select>
      </div>
      <div>B</div>
      <div>
        <select bind:value={b} on:change={changeHandler}>
          <option value="1">1位</option>
          <option value="2">2位</option>
          <option value="3">3位</option>
        </select>
      </div>
      <div>C</div>
      <div>
        <select bind:value={c} on:change={changeHandler}>
          <option value="1">1位</option>
          <option value="2">2位</option>
          <option value="3">3位</option>
        </select>
      </div>
    </div>
    <div class="font-bold">よって</div>
    <div>
      <div class="grid grid-cols-3 pl-1">
        <div>A</div>
        <div>B</div>
        <div>C</div>

        <div>{ point.a }pt</div>
        <div>{ point.b }pt</div>
        <div>{ point.c }pt</div>
      </div>
    </div>
  </div>

</div>
