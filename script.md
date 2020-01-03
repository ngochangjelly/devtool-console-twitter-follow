# This script is used to auto subscribe bunch of Twitter accounts by taking advantage of browser console

## Follow 3 steps bellow:

- Search some keyword into Twitter searchbox and click on "People" tab
<a href="https://imgur.com/OmfXc9V"><img src="https://i.imgur.com/OmfXc9V.png" title="source: imgur.com" /></a>

- Open your browser console, in this case, I use Chrome
- Now, you could use these code to paste in the console, I would explain what does each block of code do right below:

>1. select all elements which contain data-testid attribute, those are the follow button that we want to automatically click on
```
let followButtons = document.querySelectorAll("[data-testid]")
```
>2. Loop through the above HTML collection, however, use spread operator to convert it into array to easily use the array map function. Pick all of the follow buttons's data-testid attribute have the same pattern which is "follow-*", however exclude butotn with "unfollow-*" pattern
<a href="https://imgur.com/qMZLH3o"><img src="https://i.imgur.com/qMZLH3o.png" title="source: imgur.com" /></a>
```
[...followButtons].map(button=>{
if(button.getAttribute("data-testid").includes("follow") && !button.getAttribute("data-testid").includes("unfollow")){
	button.click()
}
})
```
>3. After completing 2 steps above, you would see all follow button converted to follwing, which means you have followed bunch of Twitter accounts successfully
<a href="https://imgur.com/ebfMhtR"><img src="https://i.imgur.com/ebfMhtR.png" title="source: imgur.com" /></a>

- You can scroll down and run this script again and again to repeat the action, remmber to assign followButtons = document.querySelectorAll("[data-testid]") without the "let" keyword because you have decalared it already. If you follow too many accounts, twitter would began to warn about the excessive number of accounts you can follow. Not an serious issue, you can refresh the page, wait for a few minute and continue to execute the above script.