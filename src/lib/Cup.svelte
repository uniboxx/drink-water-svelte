<script>
  let { id, fullCupsNum = $bindable() } = $props();
</script>

<div
  tabindex={id}
  role="button"
  {id}
  class={`cup cup-small ${fullCupsNum >= id ? 'full' : ''}`}
  onclick={() =>
    fullCupsNum === id ? (fullCupsNum = id - 1) : (fullCupsNum = id)}>
  250 ml
</div>

<style lang="scss">
  @use '../scss/vars';
  .cup {
    small {
      font-size: 12px;
    }

    &.cup-small {
      height: 95px;
      width: 50px;
      border-radius: 0 0 15px 15px;
      background-color: rgba(255, 255, 255, 0.9);
      cursor: pointer;
      font-size: 14px;
      align-items: center;
      justify-content: center;
      text-align: center;
      margin: 5px;
      transition: 0.3s ease;
      &.full {
        background-color: vars.$fillColor;
        color: #fff;
      }
    }
  }
</style>
