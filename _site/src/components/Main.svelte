<script lang="ts">
  import { onMount } from "svelte"

  import Fuse from "fuse.js"

  interface ImageFile {
    src: string
    folder: string
    name: string
    format: string
  }

  let images: ImageFile[] = []
  let filteredImages: ImageFile[] = []
  let search: string = ""
  let fuse: Fuse<ImageFile>

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

    fuse = new Fuse(images, {
      keys: ["folder", "name"],
    })
  })

  $: filteredImages =
    fuse && search.length
      ? fuse.search(search)?.map((result) => result.item) ?? []
      : images
</script>

<main>
  <h1>Programming VTuber Logos</h1>

  <p>
    <input type="text" placeholder="Search..." bind:value={search} />
  </p>

  <table border="1">
    <thead>
      <tr>
        <th>File</th>
        <th>Image</th>
      </tr>
    </thead>
    <tbody>
      {#if !filteredImages.length}
        <tr>
          <td colspan="2">No results found</td>
        </tr>
      {/if}
      {#each filteredImages as { src, folder, name, format }, i}
        <tr>
          <td
            ><a
              href={`https://github.com/Aikoyori/ProgrammingVTuberLogos/blob/main/${folder}/${name}`}
              target="_blank">{folder}/{name}</a
            ></td
          >
          <td><img {src} alt={name} style="width: 300px;" /></td>
        </tr>
      {/each}
    </tbody>
  </table>

  <p>
    Can't find what you're looking for? <a
      href="https://github.com/Aikoyori/ProgrammingVTuberLogos"
      target="_blank">Request a new logo</a
    >
  </p>
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

  a {
    color: white;
  }
</style>
