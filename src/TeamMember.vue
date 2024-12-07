<script setup>
const persons = [
  {
    id: 1,
    name: "Jane Doe",
    profilePhoto:
      "https://t4.ftcdn.net/jpg/05/84/65/25/360_F_584652599_s89lyUhPSMfX5YsRlKsa1AglJT7vNioO.jpg",
    jobTitle: "Software Engineer",
  },
  {
    id: 2,
    name: "Jhon Doe",
    profilePhoto:
      "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQS7lTzkUDE7wfP8zvacasdtXREAdQxo845nw&s",
    jobTitle: "Freelancer part time",
  },
  {
    id: 3,
    name: "Jasshe Doe",
    profilePhoto:
      "https://media.istockphoto.com/id/1413766112/photo/successful-mature-businessman-looking-at-camera-with-confidence.jpg?s=612x612&w=0&k=20&c=NJSugBzNuZqb7DJ8ZgLfYKb3qPr2EJMvKZ21Sj5Sfq4=",
    jobTitle: "Marketing officer",
  },
];
</script>

<template>
  <section class="container max-auto">
    <div class="py-20 bg-gray-50">
      <div class="container mx-auto px-6">
        <div>
          <h2>Team Members</h2>
          <p>
            Lorem ipsum dolor sit amet consectetur adipisicing elit. Quidem,
            ipsum impedit. Ipsa consequatur assumenda exercitationem,
            voluptatibus deleniti repellendus numquam eveniet!
          </p>
        </div>

        <div class="grid gap-12 items-center grid-cols-3">
          <div
            class="space-y-4 text-center"
            v-for="(person, index) in persons"
            :key="index"
          >
            <img
              class="mx-auto object-cover rounde-xl w-64"
              :class="index == 1 ? 'h-80' : 'h-64'"
              :src="person.profilePhoto"
              alt=""
            />
            <div>
              <h4>{{ person.name }}</h4>
              <span>{{ person.jobTitle }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped></style>
