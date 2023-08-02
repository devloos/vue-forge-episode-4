<script setup lang="ts">
// Get categories for dropdown
const { list: categories, fetchAll } = useCategories();
fetchAll();
</script>

<template>
  <div class="container max-w-[860px]">
    <!-- Code out the create project form here -->
    <h1 class="font-bold text-2xl text-start">Kickstart your own project</h1>
    <div class="grid gap-6 grid-cols-3">
      <div class="col-span-2">
        <div class="form-control">
          <label class="label">
            <span class="label-text">What is your projects name?</span>
          </label>
          <input class="input input-bordered" type="text" />
          <label class="label">
            <span class="label-text-alt text-slate-500">
              Use a very handy title that people could identify your project
            </span>
          </label>
        </div>
        <div class="form-control">
          <label class="label">
            <span class="label-text">What is your project about?</span>
          </label>
          <textarea class="textarea textarea-bordered" rows="6" />
          <label class="label">
            <span class="label-text-alt text-slate-500">
              Describe with full detail your project so that people understand
              exactly what it is about.
            </span>
          </label>
        </div>
        <AppFileUpload bucket="klkljelkj" />
        <div class="form-control">
          <label class="label">
            <span class="label-text"
              >What category does your project fit in?</span
            >
          </label>
          <select class="select select-bordered">
            <option
              v-for="category in categories"
              :key="category.uuid"
              :value="category.uuid"
            >
              {{ category.name }}
            </option>
          </select>
          <label class="label">
            <span class="label-text-alt text-slate-500">
              Selecting a fitting category ensures the right people find your
              project.
            </span>
          </label>
        </div>
        <div>
          <input
            type="range"
            min="10000"
            max="100000"
            value="25"
            class="range"
            step="15000"
          />
          <div class="w-full flex justify-between text-xs px-2">
            <span class="flex flex-col"
              ><p>|</p>
              <p>$10,000.000</p></span
            >
            <span class="flex flex-col"
              ><p>|</p>
              <p>$25,000.000</p></span
            >
            <span class="flex flex-col"
              ><p>|</p>
              <p>$50,000.000</p></span
            >
            <span class="flex flex-col"
              ><p>|</p>
              <p>$75,000.000</p></span
            >
            <span class="flex flex-col"
              ><p>|</p>
              <p>$100,000.000</p></span
            >
          </div>
        </div>
      </div>
      <ProjectCard :project="{}" category-name="dkjaklj" />
    </div>
  </div>
</template>
