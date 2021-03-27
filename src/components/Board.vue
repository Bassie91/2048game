<template>
    <div class="container">
        <ul class="board">
        <li :class="`color-`+number" :key="number.id" v-for="number in numbers">{{number}}</li>
        </ul>
        <nav>
        <i @click="moveUp" class="fas fa-arrow-circle-up"></i><br />
        <i @click="moveLeft" class="fas fa-arrow-circle-left"></i>
        <i @click="moveDown" class="fas fa-arrow-circle-down"></i>
        <i @click="moveRight" class="fas fa-arrow-circle-right"></i>
        </nav>
        <p>Your score: {{highScore}}</p>
    </div>
</template>

<script>
export default {
    name: 'Board',
    data() {
        return { 
            numbers: this.numbersArray(),
        }
    },
    methods: {
        numbersArray() {
            var numbers = [];
            var i = 0;
            for (i = 0; i<16 ; i++) {
             numbers[i] = 0;
            }
            i = Math.round(Math.random() * 15);
            numbers[i] = 2;
            i = Math.round(Math.random() * 15);
            numbers[i] = 2;
            return numbers;
        },
        moveUp() {
            var numbers = this.numbers;
            var i = 0;
            var j = 0;
            for(i=0;i<4;i++){
                for(j=0+i;j<=4*2+i;j+=4){
                    var first_number = numbers[j];
                    var second_number = numbers[j+4];
                    if(first_number===0){
                        numbers[j] = first_number + second_number;
                        numbers[j+4] = 0;
                    }
                }  
            }

            for(i=0;i<4;i++){
                for(j=0+i;j<=4*2+i;j+=4){
                    first_number = numbers[j];
                    second_number = numbers[j+4];
                    if(first_number===0){
                        numbers[j] = first_number + second_number;
                        numbers[j+4] = 0;
                    }
                }  
            }

            for(i=0;i<4;i++){
                for(j=0+i;j<=4*3+i;j+=4){
                    first_number = numbers[j];
                    second_number = numbers[j+4];
                    if(first_number===second_number){
                        numbers[j] = first_number + second_number;
                        numbers[j+4] = 0;
                    }
                }  
            }

            for(i=0;i<4;i++){
                for(j=0+i;j<=4*2+i;j+=4){
                    first_number = numbers[j];
                    second_number = numbers[j+4];
                    if(first_number===0){
                        numbers[j] = first_number + second_number;
                        numbers[j+4] = 0;
                    }
                }  
            }
            
            this.numbers = numbers;
            this.randomInsert();
        },
        moveDown() {
            var numbers = this.numbers;
            var i = 0;
            var j = 0;
            for(i=3;i>=0;i--){
                for(j=4*3+i;j>=i+4;j-=4){
                    var first_number = numbers[j];
                    var second_number = numbers[j-4];
                    if(first_number===0){
                        numbers[j] = first_number + second_number;
                        numbers[j-4] = 0;
                    }
                }  
            }

            for(i=3;i>=0;i--){
                for(j=4*3+i;j>=i+4;j-=4){
                    first_number = numbers[j];
                    second_number = numbers[j-4];
                    if(first_number===0){
                        numbers[j] = first_number + second_number;
                        numbers[j-4] = 0;
                    }
                }  
            }

            for(i=3;i>=0;i--){
                for(j=4*3+i;j>=i+4;j-=4){
                    first_number = numbers[j];
                    second_number = numbers[j-4];
                    if(first_number===second_number){
                        numbers[j] = first_number + second_number;
                        numbers[j-4] = 0;
                    }
                }  
            }

            for(i=3;i>=0;i--){
                for(j=4*3+i;j>=i+4;j-=4){
                    first_number = numbers[j];
                    second_number = numbers[j-4];
                    if(first_number===0){
                        numbers[j] = first_number + second_number;
                        numbers[j-4] = 0;
                    }
                }  
            }
            
            this.numbers = numbers;
            this.randomInsert();
        },
        moveLeft() {
            var numbers = this.numbers;
            var i = 0;
            var j = 0;
            for(i=0;i<15;i+=4){
                for(j=0+i;j<i+3;j++){
                    var first_number = numbers[j];
                    var second_number = numbers[j+1];
                    if(first_number===0){
                        numbers[j] = first_number + second_number;
                        numbers[j+1] = 0;
                    }
                }  
            }

            for(i=0;i<15;i+=4){
                for(j=0+i;j<i+3;j++){
                    first_number = numbers[j];
                    second_number = numbers[j+1];
                    if(first_number===0){
                        numbers[j] = first_number + second_number;
                        numbers[j+1] = 0;
                    }
                }  
            }

            for(i=0;i<15;i+=4){
                for(j=0+i;j<i+3;j++){
                    first_number = numbers[j];
                    second_number = numbers[j+1];
                    if(first_number===second_number){
                        numbers[j] = first_number + second_number;
                        numbers[j+1] = 0;
                    }
                }  
            }

            for(i=0;i<15;i+=4){
                for(j=0+i;j<i+3;j++){
                    first_number = numbers[j];
                    second_number = numbers[j+1];
                    if(first_number===0){
                        numbers[j] = first_number + second_number;
                        numbers[j+1] = 0;
                    }
                }  
            }
            
            this.numbers = numbers;
            this.randomInsert();
        },
        moveRight() {
            var numbers = this.numbers;
            var i = 0;
            var j = 0;
            for(i=15;i>0;i-=4){
                for(j=i;j>i-3;j--){
                    var first_number = numbers[j];
                    var second_number = numbers[j-1];
                    if(first_number===0){
                        numbers[j] = first_number + second_number;
                        numbers[j-1] = 0;
                    }
                }  
            }
            for(i=15;i>0;i-=4){
                for(j=i;j>i-3;j--){
                    first_number = numbers[j];
                    second_number = numbers[j-1];
                    if(first_number===0){
                        numbers[j] = first_number + second_number;
                        numbers[j-1] = 0;
                    }
                }  
            }

            for(i=15;i>0;i-=4){
                for(j=i;j>i-3;j--){
                    first_number = numbers[j];
                    second_number = numbers[j-1];
                    if(first_number===second_number){
                        numbers[j] = first_number + second_number;
                        numbers[j-1] = 0;
                    }
                }  
            }

            for(i=15;i>0;i-=4){
                for(j=i;j>i-3;j--){
                    first_number = numbers[j];
                    second_number = numbers[j-1];
                    if(first_number===0){
                        numbers[j] = first_number + second_number;
                        numbers[j-1] = 0;
                    }
                }  
            }
            
            this.numbers = numbers;
            this.randomInsert();
        },
        randomInsert(){
            var i = 0;
            var inserted = false;
            const newNumber = 2;
            var numbers = this.numbers;
            while(inserted==false) {
                i = Math.round(Math.random() * 15);
                if(numbers.includes(0)){
                    if(numbers[i] == 0) {
                        numbers[i] = newNumber;
                        inserted = true;
                    }
                } else {
                    console.log("Game over fool!");
                    return;
                }
            }
        },
    },
    computed: {
        highScore() {
            var numbers = this.numbers;
            var i = numbers.reduce((a,b) => Number(a) > Number(b) ? a : b);
            if(i<2048) {
                return i
            }
            else {
                console.log(i);
                return "Winner!"
                }
        },
    }
    
}
</script>


<style scoped>
.container {
    background-color: white;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 1rem;
}

.board {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    align-items: center;
    width: 80%;

}

.board li {
    list-style: none;
    flex: 0 0 25%;
    padding: 7% 0;
    border: #2c3e50 1px solid;
}

.board li.color-0 {
    background-color: rgb(248, 247, 247);
}
.board li.color-2 {
    background-color: #F0F4C3;
}
.board li.color-4 {
    background-color: #B2DFDB;
}
.board li.color-8 {
    background-color: #C5CAE9;
}
.board li.color-16 {
    background-color: #F8BBD0;
}
.board li.color-32 {
    background-color: #DCEDC8;
}
.board li.color-64 {
    background-color: #B3E5FC;
}
.board li.color-128 {
    background-color: #E1BEE7;
}
.board li.color-256 {
    background-color: #ffcdd2;
}
.board li.color-512 {
    background-color: #C8E6C9;
}
.board li.color-1024 {
    background-color: #BBDEFB;
}
.board li.color-2048 {
    background-color: #FFECB3;
}


nav {
    margin-top: 1rem;
}

nav i {
    font-size: 2rem;
    margin: 0.2rem;
    color: #2c3e50;
}

nav i:hover {
    color: #76c8ff;
}
</style>