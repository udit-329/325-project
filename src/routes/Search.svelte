<script>
  import { useLocation, Link } from "svelte-navigator";
  import * as courses from "../data/courses.json";
  const location = useLocation();

  let course = courses?.default?.find(
    (course) => course.id === $location?.search.replace("?q=", "")
  );
  console.log(course);
</script>

<div class="container-fluid">
  <div class="card shadow">
    <div class="card-header py-3">
      <p
        class="text-primary m-0 fw-bold"
        style="--bs-primary: rgb(207,154,26);--bs-primary-rgb: 207,154,26;"
      >
        <Link to={"/courses/" + course.id} class="text-primary">
          {course.id} - {course.description}
        </Link>
      </p>
    </div>
    <div class="card-body">
      <div id="dataTable" class="table-responsive table mt-2" role="grid">
        <table id="dataTable" class="table my-0">
          <thead>
            <tr>
              <th>Class</th>
              <th>Section</th>
              <th>Days</th>
              <th>Room</th>
              <th>Instructor</th>
              <th>Meeting Dates</th>
              <th>Status</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>3529</td>
              <td>100 - LEC Regular</td>
              <td>TBA</td>
              <td>TBA</td>
              <td>Blight, Stephen</td>
              <td>2022/01/10 - 2022/04/08<br /></td>
              <td><i class="fa fa-check" /><br /></td>
            </tr>
            <tr>
              <td>3540</td>
              <td>101 - LEC Regular</td>
              <td>TBA</td>
              <td>TBA</td>
              <td>Blight, Stephen</td>
              <td>2022/01/10 - 2022/04/08<br /></td>
              <td><i class="fa fa-check" /><br /></td>
            </tr>
            <tr />
            <tr />
          </tbody>
          <tfoot>
            <tr />
          </tfoot>
        </table>
      </div>
    </div>
  </div>
</div>
