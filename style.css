let question_field = document.querySelector(".question")
let answer_buttons = document.querySelectorAll(".answer")
let prav_field = document.querySelector(".prav")
let neprav_field = document.querySelector(".neprav")


function shuffle(array) {
  let currentIndex = array.length,  randomIndex;

  while (currentIndex != 0) { // Цикл повторюється до тих пір, поки залишаються елементи для перемішування
    randomIndex = Math.floor(Math.random() * currentIndex); // Вибираємо елемент, що залишився.
    currentIndex--;
    [array[currentIndex], array[randomIndex]] = [    // Міняємо місцями з поточним елементом.
      array[randomIndex], array[currentIndex]];
  }
  return array; // Повертаємо перемішаний масив
}


function randint(min, max) {
    return Math.round(Math.random() * (max - min) + min)
}

let signs = ['+', '-', '*', '/']

function getRandomSign() {
    return signs[randint(0, 3)]
}


class Question{
    constructor(){
        let a = randint(1, 50)
        let b = randint(1, 50)
        let sign = getRandomSign()
        this.question = a + " " + sign + " " + b
        if (sign == '+'){
            this.correct = a + b
        }
        else if (sign == '-'){
            this.correct = a - b
        }
        else if (sign == '*'){
            this.correct = a * b
        }else{
             this.correct = Math.round(a / b)
        }

        this.answers = [
            randint(this.correct - 15, this.correct - 1),
            randint(this.correct - 15, this.correct - 1),
            randint(this.correct + 1, this.correct + 15),
            randint(this.correct + 1, this.correct + 15),
            this.correct,
        ]
        shuffle(this.answers)
    }

    dispaly(){
        question_field.innerHTML = this.question
        for (let i = 0; i < this.answers.length; i+= 1){
            answer_buttons[i].innerHTML = this.answers[i]
        }
    }
}


let total_answers_given  = 0

let current_question = new Question()
current_question.dispaly()

let true_amount = 0
let false_amount = 0


for(let i = 0; i < answer_buttons.length; i+= 1){
    answer_buttons[i].addEventListener("click", function(){
        if(answer_buttons[i].innerHTML == current_question.correct){
            console.log("Правильно")
            answer_buttons[i].style.backgroundColor = "#0bfc03"
            anime({
                targets :answer_buttons[i],
                backgroundColor :" rgb(115, 206, 94)",
                duration: 500,
                easing: "linear",
            })
            true_amount +=1
            prav_field.innerHTML = "Правильні відповіді: " + true_amount
            
        }else{
            console.log("Неправильно")
            answer_buttons[i].style.backgroundColor = "#fc0f0c"
            anime({
                 targets :answer_buttons[i],
                backgroundColor :" rgb(115, 206, 94)",
                duration: 500,
                easing: "linear",
            })
             false_amount +=1
    neprav_field.innerHTML = "Неправильні відповіді: " + false_amount
        }
        current_question = new Question()
        current_question.dispaly()
    })

}
