<template>
    <!-- Page header with logo and tagline-->
    <header class="py-5 bg-light border-bottom mb-4">
        <div class="container">
            <div class="text-center my-5">
                <h1 class="fw-bolder">Welcome to Blog Home!</h1>
                <p class="lead mb-0">
                    A Bootstrap 5 starter layout for your next blog homepage
                </p>
            </div>
        </div>
    </header>
    <!-- Page content-->
    <div class="container">
        <div class="row">
            <!-- Blog entries-->
            <div class="col-lg-8">
                <!-- Nested row for non-featured blog posts-->
                <div class="row">
                    <BlogUnit
                        v-for="post in posts"
                        :key="post.title"
                        :post="post"
                    />
                </div>
            </div>
            <!-- Side widgets-->
            <SideWidget />
        </div>
    </div>
</template>

<script>
import BlogUnit from "./../components/blog/BlogUnit.vue";

export default {
    setup() {},
    data() {
        return {
            posts: [
                {
                    title: "one",
                    image: "https://dummyimage.com/700x350/dee2e6/6c757d.jpg",
                    body: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aliquam adipisci",
                },
                {
                    title: "two",
                    image: "https://dummyimage.com/700x351/dee2e6/6c757d.jpg",
                    body: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aliquam adipisci",
                },
                {
                    title: "three",
                    image: "https://dummyimage.com/700x352/dee2e6/6c757d.jpg",
                    body: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aliquam adipisci",
                },
                {
                    title: "four",
                    image: "https://dummyimage.com/700x350/dee2e6/6c757d.jpg",
                    body: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aliquam adipisci",
                },
                {
                    title: "five",
                    image: "https://dummyimage.com/700x350/dee2e6/6c757d.jpg",
                    body: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aliquam adipisci",
                },

                {
                    title: "six",
                    image: "https://dummyimage.com/700x350/dee2e6/6c757d.jpg",
                    body: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aliquam adipisci",
                },
                {
                    title: "seven",
                    image: "https://dummyimage.com/700x350/dee2e6/6c757d.jpg",
                    body: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aliquam adipisci",
                },
                {
                    title: "egiht",
                    image: "https://dummyimage.com/700x350/dee2e6/6c757d.jpg",
                    body: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aliquam adipisci",
                },

                {
                    title: "nine",
                    image: "https://dummyimage.com/700x350/dee2e6/6c757d.jpg",
                    body: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aliquam adipisci",
                },
                {
                    title: "ten",
                    image: "https://dummyimage.com/700x350/dee2e6/6c757d.jpg",
                    body: "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Aliquam adipisci",
                },
            ],
        };
    },
    methods: {
        getPosts() {
            // fetch("https://jsonplaceholder.typicode.com/posts?userId=1")
            //     .then((response) => response.json())
            //     .then((json) => {
            //         // console.log(json);
            //         this.posts = json;
            //     });
            this.axios
                .get("https://jsonplaceholder.typicode.com/posts?userId=1")
                .then((response) => {
                    // console.log(response.data);
                    this.posts = response.data;
                });
        },
    },
    components: {
        BlogUnit,
    },
    mounted() {
        console.log(`the component is now mounted.`);
        this.getPosts();
    },
    // created() {
    //     console.log(`the component is now created.`);
    //     this.axios
    //         .get("https://jsonplaceholder.typicode.com/posts?userId=1")
    //         .then((response) => {
    //             // console.log(response.data);
    //             this.posts = response.data;
    //         });
    // },
};
</script>
