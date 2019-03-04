<template>
    <div class="container">
       <div class="box">
            <div class="box-header">
              <h3 class="box-title">Users Table</h3>
           <button class="btn btn-success" style="float: right;" data-toggle="modal" data-target="#addNew">Add New <i class="fas fa-user-plus"></i></button>
           </div>
            <!-- /.box-header -->
            <div class="box-body">
              <div id="example1_wrapper" class="dataTables_wrapper form-inline dt-bootstrap">
                  <div class="row">
                      <div class="col-sm-6">
                          <div class="dataTables_length" id="example1_length">
                            </div>
                        </div>
                    </div>

    <div class="row">
        <div class="col-sm-12">
            <table id="example1" class="table table-bordered table-striped dataTable" role="grid" aria-describedby="example1_info">
                <thead>
                <tr role="row">
                    <th>ID</th>
                    <th>Name</th>
                    <th>Email</th>
                    <th>Type</th>
                    <th>Modify</th>
                </tr>
                </thead>
                <tbody>
                <tr role="row" class="even">
                  <td>1</td>
                  <td>Saddam Hussain</td>
                  <td>admin@mail.com</td>
                  <td>User</td>
                  <td><button class="btn btn-sm btn-info"><i class="fas fa-edit"></i></button><button class="btn btn-sm btn-danger"><i class="fas fa-trash-alt"></i></button></td>
                </tr>
                </tbody>
              </table></div>

    </div>
    </div>
</div>
            <!-- /.box-body -->
          </div>
                        <!-- Modal -->
                <div class="modal fade" id="addNew" tabindex="-1" role="dialog" aria-labelledby="addNewLabel" aria-hidden="true">
                <div class="modal-dialog modal-dialog-centered" role="document">
                    <div class="modal-content">
                    <div class="modal-header">
                        <h5 class="modal-title" id="addNewLabel">Add New</h5>
                        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                        <span aria-hidden="true">&times;</span>
                        </button>
                    </div>
                    <div class="modal-body">
                         <div class="form-group">
                            <input v-model="form.name" type="text" name="name" placeholder="Name"
                                class="form-control" :class="{ 'is-invalid': form.errors.has('name') }">
                            <has-error :form="form" field="name"></has-error>
                        </div>
                         <div class="form-group">
                            <input v-model="form.email" type="text" email="email" placeholder="Email"
                                class="form-control" :class="{ 'is-invalid': form.errors.has('email') }">
                            <has-error :form="form" field="email"></has-error>
                        </div>
                         <div class="form-group">

                            <textarea v-model="form.bio" type="text" bio="bio" placeholder="Bio"
                                class="form-control" :class="{ 'is-invalid': form.errors.has('bio') }">
                            </textarea>
                            <has-error :form="form" field="bio"></has-error>
                        </div>
                         <div class="form-group">
                            <select name="type" id="type" v-model="form.type" type="text" placeholder="Bio"
                                class="form-control" :class="{ 'is-invalid': form.errors.has('type') }">
                                <option option="">Select User Role</option>
                                <option value="admin">Admin</option>
                                <option value="user">Standard User</option>
                                <option value="author">Author</option>
                            </select>
                            <has-error :form="form" field="type"></has-error>
                        </div>
                        <div class="form-group">
                            <input v-model="form.password" type="text" password="password" placeholder="Password"
                                class="form-control" :class="{ 'is-invalid': form.errors.has('password') }">
                            <has-error :form="form" field="password"></has-error>
                        </div>

                    </div>
                    <div class="modal-footer">
                        <button type="button" class="btn btn-secondary" data-dismiss="modal">Close</button>
                        <button type="button" class="btn btn-primary">Create</button>
                    </div>
                    </div>
                </div>
                </div>
    </div>
</template>

<script>
    export default {
        data(){
            return {
                form: new Form({
                    name: '',
                    email: '',
                    password: '',
                    type: '',
                    bio: '',
                    photo: ''
                })
            }
        },
        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
