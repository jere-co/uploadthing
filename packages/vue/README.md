# @uploadthing/vue

Learn more: [docs.uploadthing.com](https://docs.uploadthing.com)

## Example

```ts
// utils/uploadthing.ts
import {
  generateUploadButton,
  generateUploadDropzone,
  generateVueHelpers,
} from "@uploadthing/vue";

export const UploadButton = generateUploadButton<OurFileRouter>();
export const UploadDropzone = generateUploadDropzone<OurFileRouter>();

export const { useUploadThing } = generateVueHelpers<OurFileRouter>();
```

```vue
<script setup lang="ts">
import type { OurFileRouter } from "server/uploadthing";

import { UploadButton, UploadDropzone } from "~/utils/uploadthing";
</script>

<template>
  <main
    class="flex min-h-screen flex-col items-center justify-center gap-16 p-24"
  >
    <div class="flex flex-col items-center justify-center gap-4">
      <span class="text-center text-4xl font-bold">
        Upload a file using a button:
      </span>

      <UploadButton
        :config="{
          endpoint: 'videoAndImage',
        }"
      />
    </div>
    <div className="flex flex-col items-center justify-center gap-4">
      <span className="text-center text-4xl font-bold">
        ...or using a dropzone:
      </span>
      <UploadDropzone
        :config="{
          endpoint: 'withMdwr',
        }"
      />
    </div>
  </main>
</template>
```
