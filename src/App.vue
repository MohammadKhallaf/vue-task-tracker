<script>
import "bootstrap/dist/css/bootstrap.css";
import "bootstrap-icons/font/bootstrap-icons.css";
export default {
  name: "App",
  components: {},
  data() {
    return {
      tasks: [],
    };
  },
  created() {
    this.tasks = [
      { id: 1, text: "test" },
      { id: 2, text: "my test" },
      { id: 3, text: "my test" },
      { id: 4, text: "my test" },
      { id: 5, text: "my test" },
    ];
  },
};
</script>

<template>
  <h1>Hello World</h1>
  <div class="container">
    <section
      class="p-3 me-auto ms-0 rounded-4"
      style="
        width: 20rem;
        max-height: 50vh;
        box-shadow: 3px 5px 10px inset;
        overflow-y: scroll;
      "
    >
      <header
        contenteditable="true"
        style="position: sticky; top: 0"
        class="bg-white"
      >
        <h1 class="py-1">Section 1</h1>
      </header>
      <article class="mt-4">
        <ul class="container d-flex flex-column" style="gap: 1rem">
          <li
            v-for="task in tasks"
            class="row fs-3 task-row border"
            v-bind:key="task.id"
          >
            <span
              class="bi-alarm col-1 d-flex align-items-center justify-content-center text-success"
            ></span>
            <span
              class="col-11 d-flex align-items-center justify-content-start"
            >
              {{ task.text }}
            </span>
          </li>
        </ul>
      </article>
    </section>
  </div>
</template>

<style>
.task-row:hover {
  font-weight: bolder;
  cursor: pointer;
}
::-webkit-scrollbar {
  display: none;
}
</style>
