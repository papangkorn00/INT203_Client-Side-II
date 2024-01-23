<template>
  <div class="w-full bg-gray-50">
    <header>
      <div
        class="flex items-center h-24 bg-gradient-to-r from-indigo-500 from-10% via-sky-500 via-30% to-emerald-500 to-90%"
      >
        <span class="m-6">
          <img src="./assets/vue-icon.png" alt="img" class="h-14" />
        </span>
        <span class="my-5 font-bold">
          <h1 class="text-white text-2xl">Creative Projects</h1>
          <h1 class="text-gray-200 text-xl">Play and Learn</h1>
        </span>
      </div>
    </header>


    <main>
      <section class="flex justify-end pt-2">
        <div
          class="w-1/4 flex items-center gap-3 border border-gray-300 p-1 rounded-lg"
        >
          <SearchIcon />
          <input
            class="outline-none"
            type="text"
            placeholder="type your keyword..."
          />
        </div>
      </section>

      <section>
        <table class="table">
          <thead class="text-xl text-black text-center">
            <tr>
              <th>ID</th>
              <th>Section</th>
              <th>GroupName</th>
              <th>Repo</th>
              <th>Members</th>
            </tr>
          </thead>
          <tbody class="text-center font-semibold">
            <tr
              v-for="data in dataGroups"
              :key="data.ID"
              class="even:bg-gray-200 text-black"
            >
              <td>{{ data.ID }}</td>
              <td>{{ data.section }}</td>
              <td>{{ data.groupName }}</td>
              <td>{{ data.repo }}</td>
              <ul>
                <li
                  class="list-disc"
                  v-for="dataMembers in data.members"
                  :key="dataMembers.ID"
                >
                  {{ dataMembers.studentId }}, {{ dataMembers.studentName }}
                </li>
              </ul>
            </tr>
          </tbody>
        </table>
      </section>
    </main>
  </div>
</template>

<script setup>
import {ref} from "vue"
import SearchIcon from "./components/icons/SearchIcon.vue"
import dataGroups from "../data/groups.json"


// const data2 = [].concat(...dataGroups)
// console.log(data2);
</script>
