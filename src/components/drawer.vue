<template>
  <div class="page-container">
    <md-app>
      <md-app-toolbar class="md-primary">
        <div class="md-layout">
            <div class="md-layout-item">{{payload.machineName}}</div>
            <div class="md-layout-item">{{payload.machineName}}</div>
            <div class="md-layout-item machine-name">
                {{payload.machineName}}
            </div>
        </div>
      </md-app-toolbar>

      <md-app-drawer md-permanent="clipped">
        <md-list>
          <md-list-item>
            <md-icon>move_to_inbox</md-icon>
            <span class="md-list-item-text">Inbox</span>
          </md-list-item>

          <md-list-item>
            <md-icon>send</md-icon>
            <span class="md-list-item-text">Sent Mail</span>
          </md-list-item>

          <md-list-item>
            <md-icon>delete</md-icon>
            <span class="md-list-item-text">Trash</span>
          </md-list-item>

          <md-list-item>
            <md-icon>error</md-icon>
            <span class="md-list-item-text">Spam</span>
          </md-list-item>
        </md-list>
      </md-app-drawer>

      <md-app-content>
        <pre>{{payload}}</pre>
      </md-app-content>
    </md-app>
  </div>
</template>

<script>
module.exports = {
    /** Allow greeting and who to be passed as parameters but provide defaults
     * @see https://vuejs.org/v2/guide/components-props.html#Prop-Validation
     */
    components: {
        'button-counter': httpVueLoader('components/button-counter.vue')
    },
    props: {
        'payload': {type: Object, default: function() { return {} }},
    },

    /** Any data must be wrapped in a fn to isolate it in case this component is used multiple times */
    data: function() { return {
    
    }}
}
</script>

<style scoped>
  .md-app {
    min-height: 350px;
    border: 1px solid rgba(#000, .12);
  }

   // Demo purposes only
  .md-drawer {
    width: 230px;
    max-width: calc(100vw - 125px);
  }
</style>