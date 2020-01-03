

elesWithAtt = document.querySelectorAll("[data-testid]")


[...elesWithAtt].map(el=>{
if(el.getAttribute("data-testid").includes("follow") && !el.getAttribute("data-testid").includes("unfollow")){
	el.click()
}
})
