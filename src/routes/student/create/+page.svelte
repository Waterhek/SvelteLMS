<script>
    import Breadcrumb from "$lib/shared/components/Breadcrumb.svelte";
    import CreateLayout from "$lib/shared/layouts/CreateLayout.svelte";
</script>

<CreateLayout title="Create Student">
    <form>
        <div class="row">
            <div class="col-sm-12 col-md-6">
                <div class="form-group">
                    <label class="form-label" for="first_name">First Name</label>
                    <input class="form-control" type="text" id="first_name" name="first_name" />
                </div>
            </div>
            <div class="col-sm-12 col-md-6">
                <div class="form-group">
                    <label class="form-label" for="last_name">Last Name</label>
                    <input class="form-control" type="text" id="last_name" name="last_name" />
                </div>
            </div>
            <div class="col-sm-12 col-md-6">
                <div class="form-group">
                    <label class="form-label" for="mobile">Mobile No</label>
                    <input class="form-control" type="text" id="mobile" name="mobile" />
                </div>
            </div>
            <div class="col-sm-12 col-md-6">
                <div class="form-group">
                    <label class="form-label" for="religion">Religion</label>
                    <input class="form-control" type="text" id="religion" name="religion" />
                </div>
            </div>
            <div class="col-sm-12 col-md-6">
                <div class="form-group">
                    <label class="form-label" for="mobile">Mobile No</label>
                    <input class="form-control" type="text" id="mobile" name="mobile" />
                </div>
            </div>
            <div class="col-sm-12 col-md-6">
                <div class="form-group">
                    <label class="form-label" for="race">Race</label>
                    <input class="form-control" type="text" id="race" name="race" />
                </div>
            </div>
            <div class="col-sm-12 col-md-6">
                <div class="form-group">
                    <label class="form-label" for="nationality">Nationality</label>
                    <input class="form-control" type="text" id="nationality" name="nationality" />
                </div>

            </div>
            <div class="col-sm-12 col-md-6">
                <div class="form-group">
                    <label class="form-label" for="password">Password</label>
                    <input class="form-control" type="password" id="password" name="password" />
                </div>
            </div>
            <div class="col-sm-12 col-md-6">
                <div class="form-group">
                    <label class="form-label" for="confirm_password">Confirm Password</label>
                    <input class="form-control" type="password" id="confirm_password" name="confirm_password" />
                </div>
            </div>
        </div>
    </form>
</CreateLayout>