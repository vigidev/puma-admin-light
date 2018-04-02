<template>
  <div id="login">
      <div class="overlay">
          <div id="logincard" class="container">
            <div class="card">
              <div class="card-body">
                  <h4 class="card-title"> Login </h4>
                  <form action="">
                      <div class="row">
                          <div class="col-md-12">
                              <fg-input type="text"
                                        label="Student ID"
                                        placeholder="Student ID"
                                        required
                              ></fg-input>
                          </div>
                      </div>
                      <div class="row">
                          <div class="col-md-12">
                              <fg-input type="password"
                                        label="password"
                                        placeholder="password"
                                        required
                              ></fg-input>
                          </div>
                      </div>
                      <div class="row justify-content-center">
                          <div class="col-md-4">
                            <button type="submit" class="btn btn-primary btn-fill">Log in</button>
                          </div>
                      </div>
                  </form>
              </div>
            </div>
          </div>
      </div>
  </div>
</template>

<script>
export default {

}
</script>

<style>
    #login{
        background-image: url("/static/img/fotopu.JPG");
        background-size: cover;
        background-position-y: -10vh;
        height: 100vh;
    }
    .overlay {
        background: rgba(0, 0, 0, 0.7);
        height: 100vh;
    }
    #logincard{
        padding-top: 30vh;
        max-width: 30vw;
    }
</style>
