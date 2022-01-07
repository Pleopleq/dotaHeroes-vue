<template>
  <transition name="modal-fade">
    <div class="modal-backdrop" @click="handleHeroModal">
      <div class="modal">
        <header class="modal-header">
          <h1>{{ title }} </h1>
          <button class="btn-close" @click="handleModalClose">X</button>
        </header>
        <div class="modal_body">
          <img :src="body.heroImg" alt="" srcset="">
        </div>
      </div>
    </div>
  </transition>
</template>

<script>
  export default {
    name: 'Modal',
    props: {
        isModalClosed: Boolean,
        handleModalClose: Function,
        title: String, 
        body: Object,
    },
  };
</script>

<style>
  .modal-backdrop {
    position: fixed;
    top: 0;
    bottom: 0;
    left: 0;
    right: 0;
    background-color: rgba(82, 80, 80, 0.329);
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .modal {
    background: #FFFFFF;
    bottom: 2rem;
    box-shadow: 2px 2px 20px 1px;
    overflow-x: auto;
    display: flex;
    flex-direction: column;
    width: 460px;
    max-width: 460px;
  }


  .modal-header {
    position: relative;
    display: flex;
    justify-content: center;
    border-bottom: 1px solid #eeeeee;
    padding: 2rem 2rem 0 2rem;
  }

  .modal_body {
    padding: 1.2rem;
  }

  .btn-close {
    position: absolute;
    top: 0;
    right: 0;
    border: none;
    font-size: 20px;
    padding: 10px;
    margin-left: 1rem;
    cursor: pointer;
    font-weight: bold;
    color: #d61515;
    background: transparent;
  }

  .modal-fade-enter,
  .modal-fade-leave-to {
    opacity: 0;
  }

  .modal-fade-enter-active,
  .modal-fade-leave-active {
    transition: opacity .5s ease;
  }
</style>