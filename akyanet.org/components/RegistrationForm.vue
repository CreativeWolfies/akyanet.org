<template>
  <slot />
  <form @submit.prevent="apiCallHere">
    <label for="email">{{ emailLabel }}</label>
    <input id="email" name="email" type="email" pattern="" />
    <label for="interest">{{ interestLabel }}</label>
    <select id="interest" name="interest">
      <option value="follow-progress">Following Akyanet progress</option>
      <option value="debate">Debating</option>
      <option value="participate">Participating and helping Akyanet</option>
    </select>
    <button type="submit">{{ submitText }}</button>
  </form>
</template>
