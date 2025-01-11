<script lang="ts">
    import { Card, CardHeader, CardBody, CardFooter } from '$lib/shared/components';
</script>

<div class="container-fluid">
    <Card>
        <CardHeader>Custom Logo</CardHeader>
        <CardBody>
            <img src="" alt="logo" />
            <form action="" method="post">
                <div class="row">
                    <div class="col-md-12 col-lg-6">
                        <div class="form-group">
                            <input type="file" class="form-control" id="logo" name="logo" />
                        </div>

                    </div>
                </div>
            </form>
        </CardBody>
        <CardFooter>
            <button class="btn btn-success" type="submit">Use Default</button>
            <button class="btn btn-primary" type="submit">Upload</button>
        </CardFooter>
    </Card>
</div>

<style>

</style>