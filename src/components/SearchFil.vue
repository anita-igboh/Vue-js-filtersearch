<template>
    <div>
        <input type="text" placeholder="Search here..." v-model="modelSearch">
        <br>
        <button @click="filterMovies" class="btn">Click</button>
        <br><br>
        <p v-for="(item, index) in result" :key="index">{{item.Name}}</p>
        
        <div class="hero">
            <div class="images" v-for="(item, index) in totalMovies" :key="index">
                <h4>{{item.Type}}</h4>
                <h3>{{item.Name}}</h3>
                <img :src="item.Url" class="red"/>
                <br><br>
                <button class="btn_img" @click="deleted(index)">Del</button>
            </div> 
          
        </div>
    </div>
</template>

<script>
export default {
    name:'SearchFil',
    data() {
        return {
            images: [
                 {
                    Name: "John Frusciante",
                    Type: "music",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151340.jpg"
                },
                {
                    Name: "Reservoir Dogs",
                    Type: "movie",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151350.jpg"
                },
                {
                    Name: "Foo Fighters",
                    Type: "music",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151360.jpg"
                },
                {
                    Name: "Pearl Jam",
                    Type: "music",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151370.jpg"
                },
                {
                    Name: "Sublime",
                    Type: "music",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151380.jpg"
                },
                {
                    Name: "Inglourious Basterds",
                    Type: "movie",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151390.jpg"
                },
                {
                    Name: "Incubus",
                    Type: "music",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151300.jpg"
                },
                {
                    Name: "Audioslave",
                    Type: "music",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151257.jpg"
                },
                {
                    Name: "Jackie Brown",
                    Type: "movie",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151358.jpg"
                },
                {
                    Name: "Nirvana",
                    Type: "music",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
                },
                {
                    Name: "The Big Lebowski",
                    Type: "movie",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
                },
                {
                    Name: "Goodfellas",
                    Type: "movie",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
                },
                {
                    Name: "Guns N' Roses",
                    Type: "music",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
                },
                {
                    Name: "Death Proof",
                    Type: "movie",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
                },
                {
                    Name: "The Offspring",
                    Type: "music",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
                },
                {
                    Name: "Django Unchained",
                    Type: "movie",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
                },
                {
                    Name: "Rage Against The Machine",
                    Type: "music",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
                },
                {
                    Name: "Snatch",
                    Type: "movie",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
                },
                {
                    Name: "Trainspotting",
                    Type: "movie",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
                },
                {
                    Name: "Weezer",
                    Type: "music",
                    Url: "http://static.tvmaze.com/uploads/images/original_untouched/60/151357.jpg"
                }
            ],
            modelSearch: '',
            result: [],
            searched: false

        }
    },
    methods: {
        deleted(index) {
            this.images.splice(index, 1)
        },
        filterMovies() {
            this.result = this.images.filter(item => { return item.Name  === this.modelSearch });
            this.searched = true;
            
        }
    },
    computed: {
        totalMovies() {
            if (this.searched) {
                return this.result;
            } else return this.images
        }
    
    }
}


</script>

<style>
.hero {
    display: grid;
    grid-template-columns: auto auto auto;
    column-gap:10px;
    row-gap:10px;
}
.red {
    width: 300px;
    height: 300px;
}
.btn_img {
    padding: 1em;
    width: 100px;
    margin-bottom: 25px;
    border-radius: 5px;
    background: rgb(241, 76, 76);
    color: white;
}
input{
    width: 300px;
    border:2px solid #aaa;
    border-radius: 20px;
    margin:8px 0;
    outline: none;
    padding:8px;
    box-sizing:border-box;
    transition:3s;
    margin-right: 10px;

}
input:focus{
    border-color: dodgerblue;
    box-shadow: 0 0 8px 0 dodgerblue;
}
.btn{
    background: black;
    text-align: center;
    padding: 5px;
    width: 100px;
    color: white;
    border-radius: 5px;

}



</style>