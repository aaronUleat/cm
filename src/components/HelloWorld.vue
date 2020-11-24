<template>
  <div class="row mt-5" @click="hideContextMenu" @contextmenu.prevent="openContextMenu($event)">
    HTML CSSResult
    <div class="jumbotron text-center">
      <h1 class="display-3">Thank You!</h1>
      <p class="lead"><strong>Please check your email</strong> for further instructions on how to complete your account setup.</p>
      <hr>
      <p>
        Having trouble? <a href="">Contact us</a>
      </p>
      <p class="lead">
        <a class="btn btn-primary btn-sm" href="https://bootstrapcreative.com/" role="button">Continue to homepage</a>
      </p>
    </div>

    Resources1×0.5×0.25×Rerun
    <ContextMenu :contextMenu="contextMenu"></ContextMenu>
  </div>
</template>

<script>
  import ContextMenu from "./ContextMenu";
  export default {
    components: {
      ContextMenu
    },
    data() {
      return {
        contextMenu: false
      }
    },
    methods: {
      openContextMenu(_evt) {
        var menu = document.getElementById("context-menu");
        if (!this.contextMenuWidth || !this.contextMenuHeight) {
          menu.style.visibility = "hidden";
          menu.style.display = "block";
          this.contextMenuWidth = menu.offsetWidth;
          this.contextMenuHeight = menu.offsetHeight;
          menu.removeAttribute("style");
        }

        if (this.contextMenuWidth + _evt.pageX >= window.innerWidth) {
          menu.style.left = _evt.pageX - this.contextMenuWidth + "px";
        } else {
          menu.style.left = _evt.pageX + "px";
        }

        if (this.contextMenuHeight + _evt.pageY >= window.innerHeight) {
          menu.style.top = _evt.pageY - this.contextMenuHeight + "px";
        } else {
          menu.style.top = _evt.pageY + "px";
        }

        menu.classList.add("active");
      },

      hideContextMenu: () => {
        document.getElementById("context-menu").setAttribute('style', 'top: -50000000%');
      }
    }
  }
</script>


