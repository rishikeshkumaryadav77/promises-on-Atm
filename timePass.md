///callbackhell on realbase example(ATM)

function select(callback1){

callback1(`selected language`)
}

function name(language,callback1){

console.log(language)
let language2 = "ENGLISH"
callback1(`have you selected language *** ${language2} *** `)
}
function enterMoney(pin, callback2){
console.log(pin)
console.log('now enter 4 digit pin')
console.log("4456")
callback2("enter Amount")
}

function withDraw(money, callback3){
console.log(money)
let amount2 = "10000"
console.log(amount2)
callback3("payment successfully")
}

select((language)=>{
name(language, (selected) =>{
enterMoney(selected, (pin)=>{
withDraw(pin, (money)=>{
console.log(money)
})
})
})
})

//promises on realbase example(ATM)

function selectLang(){
return new Promise((resolve, reject) => {
setTimeout(()=>{
resolve('Select Language')
},1000)
})
}

function pin(language){
return new Promise((resolve, reject) => {
console.log(`you have selected **** ${language} **** language`)
setTimeout(()=>{
resolve('Enter Pin')
},1000)
})
}

function amount(num){
return new Promise((resolve, reject) => {
console.log(` ${num}`)
setTimeout(()=>{
resolve('Enter Amount')
},1000)
})
}

function sucessFul(money){
return new Promise((resolve, reject) => {
console.log(` ${money}`)
setTimeout(()=>{
resolve('Payment Successfully')
},1000)
})
}

selectLang().then(res => {
console.log(res)
return pin("ENGLISH")
})
.then(pin =>{
console.log(pin)
return amount("2343")
})
.then(res =>{
console.log(res)
return sucessFul("1000")
})
.then(status =>{
console.log(status)
})
