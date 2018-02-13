### TakeMeTour Internship Program 2018

Hi all applicants! Welcome to TakeMeTour Internship Program 2018. Being and intern at TakeMeTour is challenging so we have challenges for you! These challenges are designed to assess your learning skill, which is the fundamental and most important skill of great software developer. So I do not expect you to have full or any knowledge about the topic beforehand but it's your job to try to learn and answer those challenges.

## Algorithm in Javascript
Code must be writted in Javascript language. The code will be tested with Node8, so you can use all Javascript features that equivalent to Node8.

1. Write a function that shift the elements of array to left or right by n elements in infinity loop. the function recevice 3 parameters, 1st is an array, 2nd the is direction ('left' or 'right'), 3rd is the number of elements will be shifted. For example,
```
> shift(['john', 'jane', 'sarah', 'alex'], 'left', 2)
['sarah', 'alex', 'john', 'jane']

> shift([1, 2, 3, 4 ,5], 'right', 3)
[3, 4, 5, 1, 2]
```
Answer:
```
function shift(arr,command,index) {
    let ans = []
    let arrsize = arr.length
    let pointer = command.toLowerCase() === 'right' ? arrsize-index : index
    for(let i = 0; i< arrsize;i++ ){
        ans.push(arr[(pointer++)%arrsize])
    }
    return ans
}
```
2. Download [hero.json](https://github.com/takemetour/job-quest-intern-2018/blob/master/hero.json) and write a code to caculate these values from **hero.json**
- 2.1 Average **networth** of all heroes
- 2.2 Average **level** for hero that has 'intelligent' as **primary_attribute**
- 2.3 Find the hero who got the most **assist**
- 2.4 Find the hero who got the worst **kill/death ratio** (ratio = kill/death)

Answer:
```
var json = require('./hero.json')
function calAllFunction(json) {
    let averagenetworth = 0; let averageintlevel = 0;
    let countlevelint = 0; let mostassist = "";
    let countassist = 0; let kdratio = Infinity;
    let worstkdradio = "";
    for(let i = 0 ; i< json.length ; i++){
        if(json[i].kill / json[i].death <= kdratio ){
            worstkdradio = json[i].name
            kdratio = json[i].kill / json[i].death 
        }
        if(json[i].assist >= countassist ){
            mostassist = json[i].name
            countassist = json[i].assist 
        }
        countlevelint += json[i].primary_attribute === "intelligent" ? 1 : 0
        averagenetworth += json[i].networth
        averageintlevel += json[i].primary_attribute === "intelligent" ? json[i].level : 0
    }
    averagenetworth /= json.length
    averageintlevel /= countlevelint
    console.log('Average networth of all heroes : ' + averagenetworth)
    console.log('Average level for hero INT : ' + averageintlevel)
    console.log('Most assist : ' + mostassist)
    console.log('kill/death ratio : ' + mostassist)
}
calAllFunction(json)
```

## Simple Web Application: A joke from Chuck Norris.

This part of quest will be a challenging one. You are going to make a simple web application which allow users to get some joke from **Chuck Norris** himself.

> Chuck Norris once ordered a Big Mac at Burger King, and got one.

### Features
- Users can get a joke from [Chuck Norris API](http://www.icndb.com/api/)
- Users has options to change number of result jokes, user's first name and last name
- UI Design as you wish.

### Technical description
- Using data from [REST API](http://www.icndb.com/api/)
- Any tools & framework is allowed.
- If you are using tools & framework which is same as our tech stack (React, Redux, styled-components, recompose etc.) will be a plus.
- Any extra feature will be a plus.

## Questions
Q1: What is GraphQL and how it is different from REST API?

A1: <GraphQL is a query language for APIs and a runtime for fulfilling those queries with your existing data. GraphQL provides a complete and understandable description of the data in your API, gives clients the power to ask for exactly what they need and nothing more, makes it easier to evolve APIs over time, and enables powerful developer tools. What make GraphQL different from REST API is that the endpoint you call is the identity of that object in REST API but GraphQL has the identity that is separate from how we fetch it. In REST, the shape and size of the resource is determined by the server. In GraphQL, the server declares what resources are available, and the client asks for what it needs at the time.>


Q2: Please explain how javascript benefits from cross-platform development

A2: <We can write one application and run it on several platforms. Instead of having several applications in various languages, we are able to save a lot of code and expense. The lesser code and languages that we use result for the fewer bugs, distribution and maintenance effort.>

Q3: What do you expect to get from during an internship at TakeMeTour?

A3: < Learn everything about web development and get an experience in the internship at TakeMeTour. >

## Submitting

Please fork this repo and submit your repository at jet@takemetour.com along with your contact information.

Note: These challenges must be done by yourself. There is no benefit for both sides if the answer do not reflect your true skill.
