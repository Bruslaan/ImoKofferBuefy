<template>
  <section class="container-fluid is-centered" style="margin:10px">
    <div class>
      <Stepper class />
    </div>
  </section>
</template>

<script>
import Stepper from "../components/Stepper";
import Form from "../components/Form";
export default {
  name: "HomePage",

  components: { Form, Stepper }
};
</script>
