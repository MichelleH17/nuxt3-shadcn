<script setup>
import { Tabs, TabsContent, TabsList, TabsTrigger } from '@/components/ui/tabs'

const loading = ref(false)
const list = [
  {
    title: "Today",
    component: "<div>Today</div>"
  }, {
    title: "Week",
    component: "<div>Week</div>"
  }, {
    title: "Month",
    component: "<div>Month</div>"
  }, {
    title: "Year",
    component: "<div>Year</div>"
  }
]
</script>

<template>
  <div class="grid w-full gap-4">
    <header class="flex items-start justify-between">
      <div class="grow">
        <p>Hi, welcome back Michaela!</p>
        <h1>Dashboard</h1>
      </div>
      <div class="w-[120px] h-[36px] bg-neutral-200"></div>
    </header>
    <main class="grid gap-4">
      <Tabs default-value="Today" class="w-[400px]">
        <TabsList>
          <TabsTrigger v-for="(item, index) in list" :key="index" :value="item.title">
            {{ item.title }}
          </TabsTrigger>          
        </TabsList>
        <TabsContent v-for="(item, index) in list" :key="index" :value="item.title">
          {{ item.component }}
        </TabsContent>
      </Tabs>
      <!-- <div class="flex items-center gap-4">
        <div v-for="(item, index) in 3" :key="index" class="w-[120px] h-[36px] bg-neutral-200"></div>
      </div>
      <section>
        <div class="w-full h-[360px] bg-neutral-200"></div>
      </section> -->
    </main>
    <footer class="flex items-center gap-4">
      <div v-for="(item, index) in 3" :key="index" class="w-full h-[260px] bg-neutral-200"></div>
    </footer>
  </div>
</template>