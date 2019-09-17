<template>
    <div class="candidate__group">
        <b-card>
            <b-img v-bind="mainProps" rounded="circle" alt="Circle image" :src="imgUrl"></b-img>
            <b-card-text>
                <h5><span>{{candidate.firstname}}</span><span>{{candidate.lastname}}</span></h5>
                <p>{{candidate.website}}</p>
                <p>{{candidate.phone}} | {{candidate.email}}</p>
                <p>{{candidate.address.city}}</p>
            </b-card-text>
            
        </b-card>
    </div>
</template>

<script>
export default {
    name: "Candidate",
    props: ['candidate'],
    data() {
        return {
            mainProps: { blank: false, blankColor: '#777', width: 100, height: 100, class: 'm1' },
            imgUrl: "https://picsum.photos/id/" + Math.floor(Math.random() * 101 + 100) + "/100"
        }
    }
}
</script>

<style scoped>
    .candidate__group {
        width: 100%;
    }

    .card {
        border: none;
    }

    .card-body {
        display: flex;
    }

    .card-body img {
        flex: 0 0 20%;
        max-width: 100px;
        margin: 0 20px 0 0;
    }

    .card-text {
        flex: 0 0 80%;
    }

    .card-text h5 span {
        display: inline-block;
        vertical-align: middle;
        margin: 0 10px 0 0;
        color: #17a2b8;
    }

    .card-text p {
        margin: 0;
        color: #666666;
        font-size: 14px;
    }
</style>