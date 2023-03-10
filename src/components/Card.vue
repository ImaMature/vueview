<template>
    <div class="card shadow-sm">
        <img :src="p_img2">
        <div class="card-body">
            <p class="card-text">{{ moc.p_title }}</p>
            <div class="d-flex justify-content-between align-items-center">
                <div class="btn-group">
                    <button type="button" class="btn btn-sm btn-outline-secondary">View</button>
                    <button type="button" class="btn btn-sm btn-outline-secondary">Edit</button>
                </div>
                <small class="text-muted">{{ moc.createdDate.substring(0, 10) }}</small>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: "Card",
    props: {
        moc: Object
    },
    data(){
        return{
            p_img2:require("../assets/img/props/"+this.moc.p_img)
        }
    }

}
</script>

<style scoped></style>