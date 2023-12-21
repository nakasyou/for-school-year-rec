<script lang="ts">
  import type { Point } from "../types";

  export let onChange: (point: Point) => void;

  type ClassName = "a" | "b" | "c";
  const ranking: [ClassName, ClassName, ClassName, ClassName, ClassName] = [
    "a",
    "a",
    "a",
    "a",
    "a",
  ];

  const point: Point = {
    a: 0,
    b: 0,
    c: 0,
  };

  const changeHandler = () => {
    point.a = 0
    point.b = 0
    point.c = 0

    let tmpPt = 5
    for (const ranker of ranking) {
      point[ranker] += tmpPt
      tmpPt --
    }
    onChange(point);
  };
</script>

<div>
  <div class="text-2xl">競技3 | 班対抗！紙飛行機勝負</div>
  <div class="pl-1">
    <div class="grid grid-cols-2 pl-1 gap-1">
      <div>1位</div>
      <div>
        <select bind:value={ranking[0]} on:change={changeHandler}>
          <option value="a">A</option>
          <option value="b">B</option>
          <option value="c">C</option>
        </select>
      </div>
      <div>2位</div>
      <div>
        <select bind:value={ranking[1]} on:change={changeHandler}>
          <option value="a">A</option>
          <option value="b">B</option>
          <option value="c">C</option>
        </select>
      </div>
      <div>3位</div>
      <div>
        <select bind:value={ranking[2]} on:change={changeHandler}>
          <option value="a">A</option>
          <option value="b">B</option>
          <option value="c">C</option>
        </select>
      </div>
      <div>4位</div>
      <div>
        <select bind:value={ranking[3]} on:change={changeHandler}>
          <option value="a">A</option>
          <option value="b">B</option>
          <option value="c">C</option>
        </select>
      </div>
      <div>5位</div>
      <div>
        <select bind:value={ranking[4]} on:change={changeHandler}>
          <option value="a">A</option>
          <option value="b">B</option>
          <option value="c">C</option>
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
