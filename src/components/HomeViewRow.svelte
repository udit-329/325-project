<script>
  import HomeViewButton from "./HomeViewButton.svelte";
</script>

<div class="row">
  <HomeViewButton
    name="Academic"
    icon="fas fa-school"
    routeName={"academics"}
  />
  <HomeViewButton
    name="Finances"
    icon="fas fa-dollar-sign"
    routeName={"finances"}
  />
  <HomeViewButton
    name="Your Info"
    icon="fas fa-user"
    routeName={"personal-info"}
  />
  <HomeViewButton
    name="Admissions"
    icon="fas fa-ticket"
    routeName={"admissions"}
  />
</div>
