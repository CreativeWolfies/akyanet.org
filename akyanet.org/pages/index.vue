<template>
  <header>
    <LanguageSelector /> <!-- Emits event langchange and have a prop for resource files -->
    <!-- Akyanet flag -->
    <h1>Welcome to Akyanet!</h1>
    <p>A project for freedom and equality.</p>
    <RegistrationForm>
      <h2>Register now to be notified when akyanet.org is ready!</h2>
    </RegistrationForm>
  </header>
  <section id="what-is-akyanet">
    <h2>What is Akyanet?</h2>
    <p>Akyanet is a project for creating a society where freedom, equality, respect, sharing, etc. are the core concepts.</p>
    <p>This might seem like an utopia. But we can try making this utopia a reality.</p>
    <p>This is why we need your help: without people, their opinions, their personality, we cannot build something for people.</p>
  </section>
  <section id="details">
    <h2>More details about Akyanet</h2>
    <p>The purpose of this website is to provide an interface where we can gradually apply the principles of Akyanet.</p>
    <p>Akyanet is seeking to establish an <i>anarcho-communist</i> society. But be reassured, <i>anarcho-communism</i> is not a dictatorial nor an authoritarian ideology. It is the complete opposite. There must not be a unique party system nor a central state.</p>
    <p>You can find the complete definition of what Akyanet will be <SafeLink href="https://github.com/CreativeWolfies/akyanet-research/blob/master/akyanet.md">in this document</SafeLink>.</p>
    <p>If you do not agree with the document of Akyanet, or you wish to debate about something, we are completely open to constructive critics. It is the only way we can improve Akyanet. Because without critics and debates, the people's will will not be reflected into Akyanet anymore.</p>
  <section>
  <footer>
    <ul>
      <li v-for="link in links">
        <SafeLink :href="link.href">
          <Pic
            :title="link.title"
            :alt="link.alt"
            :img-set="link.imgSet"
            :smlst-width="link.smallestWidth"
            :smlst-height="link.smallestHeight"
          />
        </SafeLink>
      </li>
    </ul>
  </footer>
</template>
