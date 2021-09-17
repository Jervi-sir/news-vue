<template>
  <div class="home">
    <main>
        <div v-for="item in items" :key="item.message" class="card">
            <a href="">Link</a>
            <img src="https://fakeimg.pl/200x100/">
            <div class="title">
                <h2>{{ item.title }}</h2>
            </div>
            <span class="date">
                {{ item.date }}
            </span>
            <p class="paragraph">
                {{item.content}}
            </p>
        </div>
    </main>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  data () {
    return {
        items: [
            {   title: 'title',
                date: 'july08 2021',
                content: 'lorem ipsum dolor sit amet consectetur' 
            },
            {   title: 'title',
                date: 'july08 2021',
                content: 'lorem ipsum dolor sit amet consectetur' 
            },
            {   title: 'title',
                date: 'july08 2021',
                content: 'lorem ipsum dolor sit amet consectetur' 
            },
            {   title: 'title',
                date: 'july08 2021',
                content: 'lorem ipsum dolor sit amet consectetur' 
            },
        ]
    }
  },
  name: 'Home',
  
}
</script>

<style scoped>

main {
    display: flex;
    flex-direction: row;
    gap: 1rem;
    flex-wrap: wrap;
}

main .card {
    display: flex;
    flex-direction: column;
    width: 25%;
}

/*2 5 8 11 14 17*/
/*2*1+0 2*2+1 2*3++2 2*4+3 2*5+4 2*6+5*/
/*2n+n-1 -- 3n-1  */
main .card:nth-last-of-type(3n){
    width: 40%;
}

main .card a {
    position: absolute;
    width: 100%;
    height: 100%;
    opacity: 0;
}

main .card {
    position: relative;
}
</style>
