<script>
function loadList() {
  let data = [
    {
      name: "Shokugeki no Souma",
      total: 24,
      current: 2,
      lastUpdated: "Sun, 09 Feb 2020 08:16:46 GMT",
    },
    {
      name: "Shingeki no Kyojin",
      total: 57,
      current: 42,
      lastUpdated: "Sun, 09 Feb 2020 08:16:46 GMT",
    }
  ]
  return data;
}

</script>


<h1>This is the home page</h1>

<div class="row">
  <div class="col-md-12">
    <h2>Add a new series</h2>
  </div>
</div>

<div class="row">
  <div class="col-md-12">
    <form>
      <div class="form-group">
        <label for="series">Series</label>
        <input type="text" class="form-control" id="seriesInput" placeholder="Enter series name">
      </div>
    </form>
  </div>
</div>

<div class="row">
  <div class="col-md-12">
    <form>
      <div class="form-group">
        <label for="search">Search</label>
        <input type="text" class="form-control" id="searchInput" placeholder="Enter search name">
      </div>
    </form>
  </div>
</div>

<div class="row">
  {#each loadList() as item}
    <div class="card m-3 col-md-5">
      <div class="row no-gutters">
        <div class="col-md-4 col-sm-3">
          <img src="https://via.placeholder.com/150" class="card-img" alt="">
        </div>
        <div class="col-md-8 col-sm-9">
          <div class="card-body">
            <h5 class="card-title">{ item.name }</h5>
            <p class="lead">Episode: { item.current }/{ item.total }</p>
            <!-- <div class="card-text">
              <div class="text-muted">
              Genre:
              <span class="badge badge-info">Light</span>
              <span class="badge badge-info">Light</span>
              </div>
            </div> -->
            <div class="btn-group" role="group" aria-label="episode counter">
              <button type="button" class="btn btn-lg btn-warning">-</button>
              <button type="button" class="btn btn-lg btn-success">+</button>
            </div>
            <p class="card-text"><small class="text-muted">Last updated on: { item.lastUpdated }</small></p>
          </div>
        </div>
      </div>
    </div>
  {/each}

</div>

<style>
.card {
  padding-left: 0;
}
</style>