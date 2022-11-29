<template>
    <header>
        <nav>
            <div>
                <h1>BOOLFLIX</h1>
            </div>
            <div>
                <span>Cerca:</span>
                <input class="searchbar" type="text">
            </div>
        </nav>
    </header>
</template>

<script>
    export default {
        name: 'HeaderComp'
    }
</script>

<style lang="scss" scoped>

    header{
        
        background-color: black;
        
        nav{
        display: flex;
        justify-content: space-between;
        padding: 20px;

        h1{
            color: red;
            font-size: 2rem;
        }

        span{
            color: white;
            font-weight: 600;
            margin-right: 10px;
        }

        .searchbar{
            width: 200px;
            height: 30px;
            border: none;
            font-size: 1.1rem;
            padding: 5px 10px;
        }

    }


    }
    

</style>