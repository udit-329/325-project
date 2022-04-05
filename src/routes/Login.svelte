<script>
  import { Link } from "svelte-navigator";
</script>

<div class="bg-gradient-primary" style="background: #12335e;">
  <div class="row justify-content-center">
    <div class="col-md-9 col-lg-12 col-xl-10">
      <div class="card shadow-lg o-hidden border-0 my-5">
        <div class="card-body p-0">
          <div class="row">
            <div class="p-5">
              <div class="text-center">
                <h4 class="text-dark mb-4">Welcome Back!</h4>
              </div>
              <form class="user">
                <div class="mb-3">
                  <input
                    id="exampleInputEmail"
                    class="form-control form-control-user"
                    type="email"
                    aria-describedby="emailHelp"
                    placeholder="Enter Email Address..."
                    name="email"
                  />
                </div>
                <div class="mb-3">
                  <input
                    id="exampleInputPassword"
                    class="form-control form-control-user"
                    type="password"
                    placeholder="Password"
                    name="password"
                  />
                </div>
                <div class="mb-3">
                  <div class="custom-control custom-checkbox small">
                    <div class="form-check">
                      <input
                        id="formCheck-1"
                        class="form-check-input custom-control-input"
                        type="checkbox"
                      /><label
                        class="form-check-label custom-control-label"
                        for="formCheck-1">Remember Me</label
                      >
                    </div>
                  </div>
                </div>
                <Link
                  class="btn btn-primary d-block btn-user w-100"
                  to="/"
                  style="background: #12335e;">Login</Link
                >
              </form>
              <div class="text-center">
                <a class="small" href="forgot-password.html">Forgot Password?</a
                >
              </div>
              <div class="text-center">
                <a class="small" href="register.html">Create an Account!</a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
