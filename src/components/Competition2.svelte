<script lang="ts">
  import type { Point } from "../types";

  export let onChange: (point: Point) => void;

  let a1 = "";
  let a2 = ""
  
  let b1 = ""
  let b2 = ""

  let c1 = "";
  let c2 = "";

  let point: Point = {
    a: 0,
    b: 0,
    c: 0,
  };

  const changeHandler = () => {
    const map = [0, 5, 3, 1];

    point.a = map[parseInt(a1)] + map[parseInt(a2)];
    point.b = map[parseInt(b1)] + map[parseInt(b2)];
    point.c = map[parseInt(c1)] + map[parseInt(c2)];

    onChange(point);
  };
</script>

<div>
  <div class="text-2xl">競技2 | 人文字コンテスト</div>
  <div class="pl-1">
    <div class="grid grid-cols-1 md:grid-cols-2">
      <div>
        <div class="text-xl">前半戦</div>
        <div class="grid grid-cols-2 pl-1 gap-1">
          <div>A</div>
          <div>
            <select bind:value={a1} on:change={changeHandler}>
              <option value="1">1位</option>
              <option value="2">2位</option>
              <option value="3">3位</option>
            </select>
          </div>
          <div>B</div>
          <div>
            <select bind:value={b1} on:change={changeHandler}>
              <option value="1">1位</option>
              <option value="2">2位</option>
              <option value="3">3位</option>
            </select>
          </div>
          <div>C</div>
          <div>
            <select bind:value={c1} on:change={changeHandler}>
              <option value="1">1位</option>
              <option value="2">2位</option>
              <option value="3">3位</option>
            </select>
          </div>
        </div>
      </div>
      <div>
        <div class="text-xl">後半戦</div>
        <div class="grid grid-cols-2 gap-1">
          <div>A</div>
          <div>
            <select bind:value={a2} on:change={changeHandler}>
              <option value="1">1位</option>
              <option value="2">2位</option>
              <option value="3">3位</option>
            </select>
          </div>
          <div>B</div>
          <div>
            <select bind:value={b2} on:change={changeHandler}>
              <option value="1">1位</option>
              <option value="2">2位</option>
              <option value="3">3位</option>
            </select>
          </div>
          <div>C</div>
          <div>
            <select bind:value={c2} on:change={changeHandler}>
              <option value="1">1位</option>
              <option value="2">2位</option>
              <option value="3">3位</option>
            </select>
          </div>
        </div>
      </div>
    </div>
    <div class="font-bold">よって</div>
    <div>
      <div class="grid grid-cols-3 pl-1">
        <div>A</div>
        <div>B</div>
        <div>C</div>

        <div>{point.a}pt</div>
        <div>{point.b}pt</div>
        <div>{point.c}pt</div>
      </div>
    </div>
  </div>
</div>
