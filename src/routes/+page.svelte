<script lang="ts">
  import { Button } from "$lib/components/ui/button";
  import * as Select from "$lib/components/ui/select/index.js";

  const fruits = [
    { value: "apple", label: "Apple" },
    { value: "banana", label: "Banana" },
    { value: "blueberry", label: "Blueberry" },
    { value: "grapes", label: "Grapes" },
    { value: "pineapple", label: "Pineapple" },
  ];
</script>

<form
  class="flex gap-2"
  on:submit|preventDefault={() =>
    alert("shouldn't happen when nothing selected")}
>
  <Select.Root required>
    <Select.Trigger class="w-[180px]">
      <Select.Value placeholder="Select a fruit" />
    </Select.Trigger>
    <Select.Content>
      <Select.Group>
        <Select.Label>Fruits</Select.Label>
        {#each fruits as fruit}
          <Select.Item value={fruit.value} label={fruit.label}>
            {fruit.label}
          </Select.Item>
        {/each}
      </Select.Group>
    </Select.Content>
    <Select.Input name="favoriteFruit" />
  </Select.Root>
  <Button type="submit">Submit</Button>
</form>
