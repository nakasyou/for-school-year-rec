<script lang="ts">
    import Competition1 from "./components/Competition1.svelte";
    import Competition2 from "./components/Competition2.svelte";

  const competition1Change = () => {

  }
</script>

<main>
  <div class="px-5">
    <div class="text-3xl">学年レク 得点集計ソフト</div>
  </div>
  <hr class="mb-2 mt-1 mx-5" />
  <div class="px-6">
    <div>
      <Competition1 onChange={competition1Change} />
      <Competition2 onChange={competition1Change} />
    </div>
  </div>
</main>
