<script>
  import { Link } from "svelte-navigator";
  import { createEventDispatcher } from "svelte";
  let q = "";

  const dispatch = createEventDispatcher();

  const toggleCart = () => {
    dispatch("toggleCart", {
      text: "toggle",
    });
  }
</script>

<nav
  class="navbar navbar-light navbar-expand bg-white shadow mb-4 topbar static-top"
>
  <div class="container-fluid">
    <div class="nav-item dropdown no-arrow">
      <a class="nav-link" href="/#" style="color: rgb(157, 25, 57);">Home</a>
    </div>
    <button
      id="sidebarToggleTop"
      class="btn btn-link d-md-none rounded-circle me-3"
      type="button"><i class="fas fa-bars" /></button
    >
    <form
      class="d-none d-sm-inline-block me-auto ms-md-3 my-2 my-md-0 mw-100 navbar-search"
    >
      <div class="input-group">
        <input
          class="bg-light form-control border-0 small"
          id="q"
          name="q"
          type="text"
          bind:value={q}
          placeholder="Search for ..."
        /><Link to={"search?q=" + q}
          ><button
            class="btn btn-primary py-0"
            type="button"
            style="background: rgb(17, 51, 93);"
            ><i class="fas fa-search" /></button
          >
        </Link>
      </div>
    </form>
    <ul class="navbar-nav flex-nowrap ms-auto">
      <li class="nav-item dropdown d-sm-none no-arrow">
        <a class="dropdown-toggle nav-link" data-bs-toggle="dropdown" href="#"
          ><i class="fas fa-search" /></a
        >
        <div class="dropdown-menu dropdown-menu-end p-3 animated--grow-in">
          <form class="me-auto navbar-search w-100">
            <div class="input-group">
              <input
                class="bg-light form-control border-0 small"
                type="text"
                placeholder="Search for ..."
              />
              <div class="input-group-append">
                <button class="btn btn-primary py-0" type="button"
                  ><i class="fas fa-search" /></button
                >
              </div>
            </div>
          </form>
        </div>
      </li>
      <li class="nav-item dropdown no-arrow mx-1">
        <div class="nav-item dropdown no-arrow">
          <a class="nav-link" href="#" style="color: rgb(157, 25, 57);">Plan</a>
        </div>
      </li>
      <li class="nav-item dropdown no-arrow mx-1">
        <div class="nav-item dropdown no-arrow">
          <a
            class="nav-link"
            href="#"
            style="color: rgb(157, 25, 57);">Enroll</a
          >
        </div>
        <div class="shadow dropdown-list dropdown-menu dropdown-menu-end" />
      </li>
      <li class="nav-item dropdown no-arrow">
        <a
          class="nav-link nav-link"
          href="#"
          style="color: rgb(157, 25, 57);">My Academics</a
        >
      </li>
      <li class="nav-item dropdown no-arrow">
        <a
          class="btn btn-primary"
          href="#"
          on:click={toggleCart}
          style="background: rgb(17, 51, 93);">Cart</a
        >
      </li>
      <div class="d-none d-sm-block topbar-divider" />
      <li class="nav-item dropdown no-arrow">
        <div class="nav-item dropdown no-arrow">
          <a class="dropdown-toggle nav-link" data-bs-toggle="dropdown" href="#"
            ><img
              class="border rounded-circle img-profile"
              src="https://res.cloudinary.com/startup-grind/image/upload/c_fill,dpr_2.0,f_auto,g_center,h_15,q_auto:good,w_15/v1/gcs/platform-data-dsc/avatars/kevin_subagaran.jpg"
              style="background:url('https://res.cloudinary.com/startup-grind/image/upload/c_fill,dpr_2.0,f_auto,g_center,h_250,q_auto:good,w_250/v1/gcs/platform-data-dsc/avatars/kevin_subagaran.jpg');"
            /></a
          >
          <div class="dropdown-menu shadow dropdown-menu-end animated--grow-in">
            <a class="dropdown-item" href="#"
              ><i
                class="fas fa-user fa-sm fa-fw me-2 text-gray-400"
              /> Profile</a
            ><a class="dropdown-item" href="#"
              ><i
                class="fas fa-cogs fa-sm fa-fw me-2 text-gray-400"
              /> Settings</a
            ><a class="dropdown-item" href="#"
              ><i class="fas fa-list fa-sm fa-fw me-2 text-gray-400" /> Activity
              log</a
            >
            <div class="dropdown-divider" />
            <Link class="dropdown-item" to="/login"
              ><i class="fas fa-sign-out-alt fa-sm fa-fw me-2 text-gray-400" />
              Logout</Link
            >
          </div>
        </div>
      </li>
    </ul>
  </div>
</nav>
