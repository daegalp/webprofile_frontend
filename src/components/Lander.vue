<template>
    <div>
        <section class="section">
            <div class="container-fliud">
                <img alt="Vue logo" class="rounded-circle" src="@/assets/dae.jpg" height="250px" width="250px">
                <h1>{{ profile.name }}</h1>
                <p>{{ profile.nrp }}</p>
                <button type="button" class="btn btn-primary btn-lg">
                  Contact
                </button>
            </div>
        </section>
        <section class="portfolio">
            <h1>Hobby</h1>
            <p>These are suppose to be my hobby</p>
            <div class="container">
                <div class="row">
                    <div class="col-md-4">
                            <div class="card">
                                <div class="card-head">
                                    <img alt="Vue logo"
                                      class="rounded-circle img-custome" src="@/assets/dota2.png">
                                    <h2>{{ profile.hobby }}</h2>
                                </div>
                                <hr>
                                <div class="card-body">
                                    <p>
                                        The first time I played Dota was in middle school, 
                                        at that time I was still playing Warcraft because Dota 2 was not yet out, 
                                        then entering high school I started playing Dota2 until now
                                    </p>
                          <button type="button" class="btn btn-outline-secondary">
                            More
                            </button>
                                </div>
                            </div>
                            <br>
                    </div>
                    <div class="col-md-4">
                            <div class="card">
                                <div class="card-head">
                                    <img alt="Vue logo" class="rounded-circle img-custome" src="https://i.pinimg.com/originals/4a/70/56/4a70563234301578c158dc142384a1c3.png">
                                    <h2>web project</h2>
                                </div>
                                <hr>
                                <div class="card-body">
                                    <p>
                                        Donec sed odio dui. Etiam porta sem malesuada magna mollis euismod. 
                                        Nullam id dolor id nibh ultricies vehicula ut id elit. 
                                        Morbi leo risus, porta ac consectetur ac, vestibulum at eros. Praesent commodo cursus magna.
                                    </p>
                                    <button type="button" class="btn btn-outline-secondary">More</button>
                                </div>
                            </div>
                        <br>
                    </div>  
                    <div class="col-md-4">
                        <div class="card">
                            <div class="card-head">
                                <img alt="Vue logo" class="rounded-circle img-custome" src="https://cdn.mos.cms.futurecdn.net/wH5y2PkWhCxqKBje8rBp5e.jpg">
                                <h2>web project</h2>
                            </div>
                            <hr>
                            <div class="card-body">
                                <p>
                                    Donec sed odio dui. Etiam porta sem malesuada magna mollis euismod. 
                                    Nullam id dolor id nibh ultricies vehicula ut id elit. 
                                    Morbi leo risus, porta ac consectetur ac, vestibulum at eros. Praesent commodo cursus magna.
                                </p>
                                <button type="button" class="btn btn-outline-secondary">More</button>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </div>
</template>

<script>
    import axios from 'axios';

    export default {
        data() {
            return {
                profile: [],
                errors: []
            }
        },

        // Fetches posts when the component is created.
        created() {
            axios.get(`/api/profiles`)
            .then(response => {
                // JSON responses are automatically parsed.
                this.profile = response.data[0]
            })
            .catch(e => {
                this.errors.push(e)
            })
        }
    }
</script>

<style lang="css" scoped>
    .section{
        padding-top: 10%;
        padding-bottom: 10%;
    }
    .portfolio{
        background-color: #34345238;
        padding-top: 8%;
        padding-bottom: 15%;
        /* padding:15% */
    }
    .img-custome{
        width: 140px;
        height: 140px;
        margin-top: 15px;
    }
</style>