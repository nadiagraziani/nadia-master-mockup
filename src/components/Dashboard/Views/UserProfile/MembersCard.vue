<template>
  <div class="card">
    <div class="header">
      <h4 class="title">{{title}}</h4>
    </div>
    <div class="content">
      <ul class="list-unstyled team-members">
        <li>
          <div class="row" v-for="member in members">
            <div class="col-xs-3">
              <div class="avatar">
                <img :src="member.image" alt="Circle Image" class="img-circle img-no-padding img-responsive">
              </div>
            </div>
            <div class="col-xs-6">
              {{member.name}}
              <br>
              <span :class="getStatusClass(member.status)">
                <small>{{member.status}}</small>
              </span>
            </div>

            <div class="col-xs-3 text-right">
              <button class="btn btn-sm btn-success btn-icon">
                <i class="fa fa-envelope"></i>
              </button>
            </div>
          </div>
        </li>
      </ul>
    </div>
  </div>
</template>
<script>
  export default {
    data () {
      return {
        title: 'Membri Staff',
        members: [
          {
            image: 'static/img/faces/face-0.jpg',
            name: 'Nadia Graziani',
            status: 'Offline'
          },
          {
            image: 'static/img/faces/face-1.jpg',
            name: 'Mirco Attocchi',
            status: 'Available'
          },
          {
            image: 'static/img/faces/face-1.jpg',
            name: 'Elis Graziani',
            status: 'Busy'
          }
        ]
      }
    },
    methods: {
      getStatusClass (status) {
        switch (status) {
          case 'Offline':
            return 'text-muted'
          case 'Available':
            return 'text-success'
          case 'Busy':
            return 'text-danger'
          default:
            return 'text-success'
        }
      }
    }
  }

</script>
<style>

</style>
