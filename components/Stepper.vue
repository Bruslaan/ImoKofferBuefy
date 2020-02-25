<template>
  <section>
    <b-steps v-model="activeStep">
      <template v-for="(step, index) in steps">
        <b-step-item v-if="step.displayed" :key="index" :label="step.label">
          <div v-if="index==0" class="container is-centered" style="max-width:60vh">
            <Form style="padding-top: 10px; padding-bottom:10px" />
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Rem distinctio optio dolor dolore porro similique repudiandae, consectetur deleniti voluptate et consequatur nihil! Ut nam blanditiis doloribus? Laborum illo repudiandae accusantium.</p>
            <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Iusto vitae quis et veritatis, possimus quasi voluptatem molestias illo facere praesentium culpa corporis, laboriosam a, quidem enim porro? Omnis, non et.</p>
          </div>
          <div v-if="index==1" class="container is-centered center">
            <h1>Test Shit</h1>
            <p>
              Deine Mudda adasdasdasdasdasd asd a dada
              dasdadas
              dasdadasdadasd
            </p>

            <b-field>
              <b-upload v-model="dropFiles" multiple drag-drop>
                <section class="section">
                  <div class="content has-text-centered">
                    <p>
                      <b-icon icon="upload" size="is-large"></b-icon>
                    </p>
                    <p>Drop your files here or click to upload</p>
                  </div>
                </section>
              </b-upload>
            </b-field>

            <div class="tags">
              <span v-for="(file, index) in dropFiles" :key="index" class="tag is-primary">
                {{file.name}}
                <button
                  class="delete is-small"
                  type="button"
                  @click="deleteDropFile(index)"
                ></button>
              </span>
            </div>
          </div>
        </b-step-item>
      </template>

      <template slot="navigation" slot-scope="{previous, next}">
        <div class="sticky container is-centered">
          <b-button outlined :disabled="previous.disabled" @click.prevent="previous.action">Previous</b-button>
          <b-button outlined :disabled="next.disabled" @click.prevent="next.action">Next</b-button>

          <b-button outlined disabled="true">Generate PDF</b-button>
        </div>
      </template>
    </b-steps>
  </section>
</template>

<script>
import Form from "./Form";
export default {
  components: { Form },
  data() {
    return {
      activeStep: 0,
      showMusic: true,
      showBooks: false,
      dropFiles: []
    };
  },
  methods: {
    deleteDropFile(index) {
      this.dropFiles.splice(index, 1);
    }
  },
  computed: {
    baseSteps() {
      return [
        {
          label: "Formular",
          content: "Lorem ipsum dolor sit amet.",
          displayed: true
        },
        {
          label: "Unterlagen",
          content: "Lorem ipsum dolor sit amet.",
          displayed: true
        },
        {
          label: "Keine Ahnung",
          content: "Lorem ipsum dolor sit amet.",
          displayed: true
        }
      ];
    },
    steps() {
      const steps = [...this.baseSteps];
      if (this.showBooks) {
        steps.splice(steps.length - 1, 0, this.bookStep);
      }
      return steps;
    },
    bookStep() {
      return {
        label: "Books",
        content: "Lorem ipsum dolor sit amet.",
        displayed: true
      };
    }
  }
};
</script>