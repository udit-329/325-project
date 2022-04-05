<script>
  import { Router, Route } from "svelte-navigator";
  import Navbar from "./components/Navbar.svelte";
  import Cart from "./components/Cart.svelte";
  import HomeViewRow from "./components/HomeViewRow.svelte";
  import * as courses from "./data/courses.json";
  import Academics from "./routes/Academics.svelte";
  import Finances from "./routes/Finances.svelte";
  import Search from "./routes/Search.svelte";
  import Courses from "./routes/Courses.svelte";
  import Login from "./routes/Login.svelte";

  let CartOpen = false;
  const toggle = () => (CartOpen = !CartOpen);
  window.cartData = [];

  function courseHandle(event) {
    console.log(event.detail.text)
    let course = courses?.default?.find((course) => course.id === event.detail.text);
    window.cartData.push(course);
  }
</script>

<main>
  <Router>
    <Route path="/">
      <Navbar on:toggleCart={toggle}/>
      <div class="container-fluid">
        <HomeViewRow />
      </div>
    </Route>
    <Route path="/login">
      <div class="container-fluid">
        <Login />
      </div>
    </Route>
    <Route path="/academics">
      <Navbar on:toggleCart={toggle}/>
      <div class="container-fluid">
        <HomeViewRow />
        <Academics />
      </div>
    </Route>
    <Route path="/finances">
      <Navbar on:toggleCart={toggle}/>
      <div class="container-fluid">
        <HomeViewRow />
        <Finances />
      </div>
    </Route>
    <Route path="/search">
      <Navbar on:toggleCart={toggle}/>
      <div class="container-fluid">
        <HomeViewRow />
        <Search />
      </div>
    </Route>
    <Route path="/courses/:id" let:params>
      <Navbar on:toggleCart={toggle}/>
      <div class="container-fluid">
        <HomeViewRow />
        <Courses on:courseId={courseHandle} id={params.id} />
      </div>
    </Route>
  </Router>

  {#if CartOpen}
    <Cart on:closePopup={toggle} />
  {/if}
</main>
