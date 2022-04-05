<script>
  import { Link } from "svelte-navigator";

  let colour = "";

  function handleMouseOver(e) {
    colour = "color: rgb(17, 51, 93);";
  }

  function handleMouseOut(e) {
    colour = "";
  }

  export let name;
  export let icon;
  export let routeName;
  let styles = `fas ${icon} fa-2x text-gray-300`;
</script>

<div
  class="col-md-6 col-xl-3 mb-4"
  on:mouseover={handleMouseOver}
  on:mouseout={handleMouseOut}
>
  <div class="card shadow border-start-info py-2">
    <div class="card-body">
      <div class="row align-items-center no-gutters">
        <div class="col me-2">
          <div class="text-uppercase text-info fw-bold text-xs mb-1">
            <Link to={"/" + routeName}>
              <span style="font-size: 18px;color: rgb(157, 25, 57);"
                >{name}</span
              >
            </Link>
          </div>
        </div>
        <div class="col-auto">
          <i class={styles} style={colour} />
        </div>
      </div>
    </div>
  </div>
</div>
