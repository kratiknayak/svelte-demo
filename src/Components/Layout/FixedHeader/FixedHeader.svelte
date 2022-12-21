<div class="fixed-header">
		<slot name="header">
      <span>Couldn't load header</span>
		</slot>
		<slot name="megaMenu">
      <span>Couldn't load mega menu</span>
		</slot>
</div>

<style>
  .fixed-header{
    position: sticky;
    top: 0;
    border-bottom: 1px solid #bcbcbc6b;
    z-index: 10;
  }

</style>