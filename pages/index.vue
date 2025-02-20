<script setup>
const { auth } = useSupabaseClient()
const user = useSupabaseUser()

const logout = async () => {
  await auth.signOut()
  navigateTo('/login')
}

console.log(user.value.user_metadata.firstname)
console.log(user.value.user_metadata.lastname)
const userFirstName = user.value.user_metadata.firstname
const userLastName = user.value.user_metadata.lastname

</script>
<template>
  <h1>Welcome {{ userFirstName }} {{ userLastName }}</h1>
  <UButton @click='logout' label="signout" />
</template>
