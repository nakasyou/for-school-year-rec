<script lang="ts">
  import Competition1 from "./components/Competition1.svelte";
  import Competition2 from "./components/Competition2.svelte";
  import Competition3 from "./components/Competition3.svelte";

  import type { Point } from "./types"

  const points: [Point, Point, Point] = [
    {a: 0, b: 0, c: 0},
    {a: 0, b: 0, c: 0},
    {a: 0, b: 0, c: 0}
  ]
  const competitionChange = (index: number) => {
    return (point: Point) => {
      points[index] = point
    }
  }
  let point: Point = {
    a: 0,
    b: 0,
    c: 0
  }
  $: {
    point.a = points.map(point => point.a).reduce((pre, current) => pre + current, 0)
    point.b = points.map(point => point.b).reduce((pre, current) => pre + current, 0)
    point.c = points.map(point => point.c).reduce((pre, current) => pre + current, 0)
  }
</script>

<main>
  <div class="px-5">
    <div class="text-3xl">学年レク 得点集計ソフト</div>
  </div>
  <hr class="mb-2 mt-1 mx-5" />
  <div class="px-6">
    <div class="flex flex-col gap-5">
      <Competition1 onChange={competitionChange(0)} />
      <Competition2 onChange={competitionChange(1)} />
      <Competition3 onChange={competitionChange(2)} />
    </div>
    <div>
      <div class="text-2xl">Result</div>
      <div class="grid grid-cols-3 text-lg pl-2">
        <div>A</div>
        <div>B</div>
        <div>C</div>

        <div>{ point.a } pt</div>
        <div>{ point.b } pt</div>
        <div>{ point.c } pt</div>
      </div>
    </div>
  </div>
</main>
