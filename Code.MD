

//FUNCTIONS PART 1


//Average calculator

function avg(arr) {
    let total = 0;
    for (let num of arr) {
        total += num;
    }
    return total / arr.length;
}

//Password validator

function isValidPassword(password, username) {
    if (
        password.length < 8 ||
        password.indexOf(' ') !== -1 ||
        password.indexOf(username) !== -1) {
        return false;
    }
    return true
}

//Pangram validator

function isPangram(sentence) {
    let lowerCased = sentence.toLowerCase();
    for (let char of 'abcdefghijklmnopqrstuvwxyz') {
        if (!lowerCased.includes(char)) {
            return false;
        }
    }
    return true;
}

//Get playing card

function pick(arr) {
    const idx = Math.floor(Math.random() * arr.length);
    return arr[idx];
}

function getCard() {
    const values = [
        '1', '2', '3', '4', '5', '6', '7', '8', '9', '10',
        'J', 'Q', 'K', 'A'
    ];
    const suits = ['picas', 'espadas', 'corazones', 'diamantes'];
    return { value: pick(values), suit: pick(suits) };
}


//FUNCTIONS PART 2


//Scope

let bird = 'mandarin duck';

function birdWach() {
    let bird = 'golden pheasant';
    console.log(bird);
}
birdWach();
console.log(bird);

//Block scope

function doubleArr(arr) {
    const result = [];
    for (let num of arr) {
        let double = num * 2;
        result.push(double);
    }
    return result;
}

//Lexical scope

function outer() {
    let hero = "Black Panter";

    function inner() {
        let cryForHelp = `${hero}, please save me!`
        console.log(cryForHelp);
    }
    inner();
}


function sayHi() {
    let user = "Fede";

    function greet() {
        let welcome = `Welcome, ${user}!`
        console.log(welcome);
    }
    greet();
}

//Expressions

const square = function (num) {
    return num * num;
}

//Arguments

function greet() {
    console.log("Hello!");
}

function repeatNTimes(action, num) {
    for (let i = 0; i < num; i++) {
        action();
    }
}
repeatNTimes(greet, 3);

//Return values

function multiplyBy(num) {
    return function (x) {
        return x * num;
    }
}
const triple = multiplyBy(3);


function makeBetweenFunc(x, y) {
    return function (num) {
        return num >= x && num <= y;
    }
}
const isChild = makeBetweenFunc(0, 10);

//Callback

setTimeout(function () {
    alert("Hello there!")
}, 3000);

function answer() {
    alert("General Kenobi")
}
const btn = document.querySelector('button');
btn.addEventListener('click', answer);


//FUNCTIONS PART 3


//ForEach

const books = [{
    title: 'Good Omens',
    author: ['Terry Pratchett', 'Neil Gaiman'],
    rating: 4.25
},
{
    title: 'Bone: The Complete Edition',
    author: ['Jeff Smith'],
    rating: 4.42
},
{
    title: 'American Gods',
    author: ['Neil Gaiman'],
    rating: 4.11
},
{
    title: 'A Gentleman in Moscow',
    author: ['Amor Towels'],
    rating: 4.36
}]

books.forEach(function (book) {
    console.log(book.title.toUpperCase())
})

//Map

const texts = ['rofl', 'lol', 'omg', 'ttyl'];
const caps = texts.map(function(t) {
    return t.toUpperCase();
})
