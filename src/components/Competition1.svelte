<script lang="ts">
  import type { Point } from '../types'

  export let onChange: (point: Point) => void

  let ac = ''
  let ab = ''
  let bc = ''

  let point: Point = {
    a: 0, b: 0, c: 0
  }
  const calcPoint = (className: string, fightA: string, fightB: string) => {
    let pt = 0

    if (fightA === `${className}-2`) {
      pt += 7
    } else if (fightA === `${className}-1`) {
      pt += 5
    } else {
      pt += 1
    }

    if (fightB === `${className}-2`) {
      pt += 7
    } else if (fightB === `${className}-1`) {
      pt += 5
    } else {
      pt += 1
    }
    return pt
  }
  const changeHandler = () => {
    point.a = calcPoint('a', ac, ab)
    point.b = calcPoint('b', ab, bc)
    point.c = calcPoint('c', ac, bc)

    onChange(point)
  }
</script>
<div>
  <div class="text-2xl">競技1 | 王様は誰だ!? 王様ドッヂボール</div>
  <div class="pl-1">
    <div class="grid grid-cols-2 pl-1 gap-1">
      <div>A vs C</div>
      <div>
        <select bind:value={ac} on:change={changeHandler}>
          <option value="none">---</option>

          <option value="a-2">Aが王様当てた</option>
          <option value="c-2">Cが王様当てた</option>

          <option value="a-1">Aが普通に勝った</option>
          <option value="c-1">Cが普通に勝った</option>
        </select>
      </div>
      <div>A vs B</div>
      <div>
        <select bind:value={ab} on:change={changeHandler}>
          <option value="none">---</option>

          <option value="a-2">Aが王様当てた</option>
          <option value="b-2">Bが王様当てた</option>

          <option value="a-1">Aが普通に勝った</option>
          <option value="b-1">Bが普通に勝った</option>
        </select>
      </div>
      <div>B vs C</div>
      <div>
        <select bind:value={bc} on:change={changeHandler}>
          <option value="none">---</option>

          <option value="b-2">Bが王様当てた</option>
          <option value="c-2">Cが王様当てた</option>

          <option value="b-1">Bが普通に勝った</option>
          <option value="-1">Cが普通に勝った</option>
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
