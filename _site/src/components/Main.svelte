<script lang="ts">
  import { onMount } from "svelte"

  interface ImageFile {
    src: string
    folder: string
    name: string
    format: string
  }

  let images: ImageFile[] = []

  onMount(async () => {
    const files = await import.meta.glob<{
      default: { src: string; format: string }
    }>(["../../../**/*.{png,svg}", "!../../../_site/**/*"], { eager: true })

    images = Object.keys(files)
      .map((file) => {
        const { src, format } = files[file].default

        return {
          src,
          folder: file.split("/").slice(-2, -1).pop(),
          name: file.split("/").pop(),
          format,
        }
      })
      .filter((image) => !image.name.includes("Old.")) // Filter out images with "Old." in the name
  })
</script>

<main>
  <table border="1">
    <thead>
      <tr>
        <th>Path</th>
        <th>Image</th>
      </tr>
    </thead>
    <tbody>
      {#each images as { src, folder, name, format }, i}
        <tr>
          <td>{folder}/{name}</td>
          <td><img {src} alt={name} style="width: 300px;" /></td>
        </tr>
      {/each}
    </tbody>
  </table>
</main>

<style>
  main {
    margin: auto;
    padding: 1rem;
    width: 800px;
    max-width: calc(100% - 2rem);
    color: white;
    font-size: 20px;
    line-height: 1.6;
  }

  td {
    padding: 2rem 1rem;
  }
</style>
