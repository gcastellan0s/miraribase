<template>
  <div>
    <b-alert show variant="light" class="alert alert-elevate">
      <div class="alert-icon">
        <i class="flaticon-warning kt-font-brand"></i>
      </div>
      <div class="alert-text">
        <b>Breadcrumb</b> Indicate the current page's location within a
        navigational hierarchy. Separators are automatically added in CSS
        through ::before and content.
        <a
          class="kt-link kt-link--brand kt-font-bold"
          href="https://bootstrap-vue.js.org/docs/components/breadcrumb"
          target="_blank"
        >
          See documentation.
        </a>
      </div>
    </b-alert>

    <KTCodePreview v-bind:title="'Breadcrumb'">
      <template v-slot:preview>
        <b-breadcrumb :items="code1.items"></b-breadcrumb>
      </template>
      <template v-slot:html>
        {{ code1.html }}
      </template>
      <template v-slot:js>
        {{ code1.js }}
      </template>
    </KTCodePreview>

    <KTCodePreview v-bind:title="'Manually placed items'">
      <template v-slot:preview>
        <p>
          You may also manually place individual <code></code> child components
          in the default slot of the
          <code>&lt;b-breadcrumb-item&gt;</code> component, as an alternative to
          using the <code>&lt;b-breadcrumb&gt;</code> prop, for greater control
          over the content of each item:codeitems
        </p>
        <b-breadcrumb>
          <b-breadcrumb-item href="#home">
            <b-icon
              icon="house-fill"
              scale="1.25"
              shift-v="1.25"
              aria-hidden="true"
            ></b-icon>
            Home
          </b-breadcrumb-item>
          <b-breadcrumb-item href="#foo">Foo</b-breadcrumb-item>
          <b-breadcrumb-item href="#bar">Bar</b-breadcrumb-item>
          <b-breadcrumb-item active>Baz</b-breadcrumb-item>
        </b-breadcrumb>
      </template>
      <template v-slot:html>
        {{ code2.html }}
      </template>
    </KTCodePreview>
  </div>
</template>

<script>
import KTCodePreview from "@/views/partials/content/CodePreview.vue";
import { SET_BREADCRUMB } from "@/store/breadcrumbs.module";

export default {
  data() {
    return {
      code1: {
        html: `<b-breadcrumb :items="items"></b-breadcrumb>`,
        js: `export default {
    data() {
      return {
        items: [
          {
            text: 'Admin',
            href: '#'
          },
          {
            text: 'Manage',
            href: '#'
          },
          {
            text: 'Library',
            active: true
          }
        ]
      }
    }
  }`,
        items: [
          {
            text: "Admin",
            href: "#"
          },
          {
            text: "Manage",
            href: "#"
          },
          {
            text: "Library",
            active: true
          }
        ]
      },

      code2: {
        html: `<b-breadcrumb>
  <b-breadcrumb-item href="#home">
    <b-icon icon="house-fill" scale="1.25" shift-v="1.25" aria-hidden="true"></b-icon>
    Home
  </b-breadcrumb-item>
  <b-breadcrumb-item href="#foo">Foo</b-breadcrumb-item>
  <b-breadcrumb-item href="#bar">Bar</b-breadcrumb-item>
  <b-breadcrumb-item active>Baz</b-breadcrumb-item>
</b-breadcrumb>`
      }
    };
  },
  components: {
    KTCodePreview
  },
  mounted() {
    this.$store.dispatch(SET_BREADCRUMB, [
      { title: "Vue Bootstrap", route: "alert" },
      { title: "Breadcrumb" }
    ]);
  }
};
</script>
