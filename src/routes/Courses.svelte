<script>
  import * as courses from "../data/courses.json";
  export let id;
  import { createEventDispatcher } from "svelte";
  let course = courses?.default?.find((course) => course.id === id);

  let button_text="Add to Cart"

  // function handleClick() {
  //   button_text = "Added to Cart!"

  //   var button_ob = document.getElementById('buy-button'
  //   button_ob.classList.add('btn-added-to-cart')

  //   window.cartData.push(course);
  // }

  const dispatch = createEventDispatcher();

    const handleClick = () => {
        // console.log(event.target.classList)
        button_text = "Added to Cart!"
        var button_ob = document.getElementById('buy-button')
        button_ob.classList.add('btn-added-to-cart')
        dispatch("courseId", {
            text: id,
            });
        
    }
</script>

{#if course?.id}
  <div class="row">
    <div class="card shadow mb-4">
      <div class="card-header py-3">
        <h6 class="text-primary fw-bold m-0">Class Detail</h6>
      </div>
      <ul class="list-group list-group-flush">
        <li class="list-group-item">
          <div class="row align-items-center no-gutters">
            <div class="col me-2">
              <h6 class="mb-0" style="height: 43.8113px;">
                <strong>{course.id} - {course.description}</strong><span
                  style="font-size: 12px;"
                  ><br />Queen&#39;s University | 2022 Winter | Lecture<br /><br
                  /></span
                ><br />
              </h6>
            </div>
          </div>
        </li>
        <li class="list-group-item">
          <div class="row align-items-center no-gutters">
            <div class="col me-2">
              <h6 class="mb-0" style="height: 43.8113px;">
                <strong>Details</strong><span style="font-size: 12px;"
                  ><br /><strong>Status:</strong> Open
                  <strong>CourseID:</strong>
                  201431 <br /><br /></span
                ><br />
              </h6>
            </div>
          </div>
        </li>
        <li class="list-group-item">
          <div class="row align-items-center no-gutters">
            <div class="col me-2">
              <h6 class="mb-0" style="height: 69.8113px;">
                <strong>Meeting Information</strong><span
                  style="font-size: 12px;"
                  ><br /><strong
                    >Days &amp; Times       | Room                 | Instructor
                    | Meeting Dates</strong
                  ><br />Mon 3:30-4:30pm | Kingston RM101 | Prof            |
                  2022/01/10 - 2022/04/08 <br /><br /></span
                ><br />
              </h6>
            </div>
          </div>
        </li>
        <li class="list-group-item">
          <div class="row align-items-center no-gutters">
            <div class="col me-2">
              <h6 class="mb-0" style="height: 43.8113px;">
                <strong>Class Availability</strong><span
                  style="font-size: 12px;"
                  ><br /><strong>Class Capacity:</strong> 122
                  <strong>Wait List Capacity:</strong>
                  13<br /></span
                ><br />
              </h6>
            </div>
          </div>
        </li>
        <li class="list-group-item">
          <div class="row align-items-center no-gutters">
            <div class="col me-2">
              <h6 class="mb-0" style="height: 43.8113px;">
                <strong>Description</strong><span style="font-size: 12px;"
                  ><br />Engineering practices, wow<br /><br /></span
                ><br />
              </h6>
            </div>
          </div>
        </li>
        <li class="list-group-item">
          <div class="row align-items-center no-gutters">
            <div class="col me-2">
              <div
                id='buy-button'
                class="btn btn-primary"
                type="button"
                on:click|once={handleClick}>{button_text}</div
              >
            </div>
          </div>
        </li>
      </ul>
    </div>
  </div>
{/if}

<style>
  :global(.btn-added-to-cart) {
    background-color: #f5f5f5 !important;
    color: #000 !important;
    cursor: default !important;
  }
</style>