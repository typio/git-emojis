<script lang="ts">
  let toasts = [];

  export const addToast = (
    title: string,
    description: string,
    duration: number
  ) => {
    toasts.push({
      title,
      description,
    });
    setTimeout(() => {
      toasts = toasts.slice(1);
    }, duration);
    toasts = toasts;
  };
</script>

<div
  class="fixed pointer-events-none bottom-0 right-0 z-50 flex flex-col items-end w-full max-w-sm p-4 mx-4 my-6 space-y-4"
>
  {#each toasts as toast}
    <div
      class="flex items-center w-full p-4 space-x-4 bg-white rounded-lg shadow-lg dark:bg-slate-800"
    >
      <div
        class="flex items-center justify-center flex-shrink-0 w-10 h-10 text-2xl rounded-full"
      >
        ✅
      </div>
      <div>
        <p class="text-sm font-medium text-slate-700 dark:text-slate-200">
          {toast.title}
        </p>
        <p class="text-lg text-slate-600 dark:text-slate-400">
          {toast.description}
        </p>
      </div>
    </div>
  {/each}
</div>
