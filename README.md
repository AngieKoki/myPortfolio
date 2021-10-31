# MY PORTFOLIO
## ABOUT MY PORTFOLIO
myPortfolio is a website parading all public repositories on github account greatsilas23 http://github.com/greatsilas23

## STEPS FOLLOWED TO BUILD MY PORTFOLIO
### Feasibility Study
### Economical
myPortfolio helps new users to discover the github account of greatsilas23 hence allowing forming collaborations and future project ideas using minimal economic resources offered free by Github Pages
### Technical
myPortfolio uses HTML and CSS to deliver a user experince that is immersive yet light on the processor
### Legal
myPortfolio does not violate any copywright laws
### Scheduling Consideration
myPortfolio was developed on 01/10/2021 and it is to be deployed to Github Pages on 31/10/2021
## System Analysis
### Input
myPortfolio uses forms to accept input. It accepts text input for username and email. It accepts only numerical input for age
### Process
myPortfolio uses linear search algorithm to handle user search requests which runs in O(log n) time
### Output
myPortfolio uses tables to display reports to the user
## System Design
### Webpage Layout
#### Header
a container that displays the name of the developer
#### Side Navigation Bar
a container that allows users to jump to different sections of the webpage
#### Main Display
a container that displays results of searches and available actions
#### Footer
a container that displays copywright information
### Webpage Responsiveness
#### Sliding Navigation Bar
a container that is animated into the page to show additional actions 
#### Popup
a container that is hidden by default but displayed once the user requests it
## Programming And Testing
### Frontend development
#### Input
myPortfolio uses the following javascript code to insert data
```html
	<div>
		<form>
			<input type="text" id="usrName">
			<input type="number" id="usrAge">
			<input type="text" id="usrEmail">
			<input type="submit" onclick="setItem()">
		</form>
	</div>
```
```javascript
	Array userData = new Array()
	function setItem(){
		let usrName = document.getElementById("usrName").value 
		let usrAge = document.getElementById("usrAge").value 
		let usrEmail = document.getElementById("usrEmail").value 
		userData.push({
			usrName : usrName,
			usrAge : usrAge,
			usrEmail: usrEmail
		})
		localStorage.setItem("userData", userData) 	
	}
```
### Data-Handling architecture
#### Output
myPortfolio uses the following javascript code to fetch data
```html
	<div>
		<form>
			<input type="text" id="name">
			<input type="number" id="age">
			<input type="text" id="email">
			<input type="submit" onclick="getItem()">
		</form>
	</div>
	<div>
		<table id="viewData">
			<tr>
				<th>Name</th>
				<th>Age</th>
				<th>Email</th>
			</tr>
		</table>
	</div>
```
```javascript
	Array userData = new Array()
	function getItem(){
		let usrName = document.getElementById("name").value 
		let usrAge = document.getElementById("age").value 
		let usrEmail = document.getElementById("email").value 
		let instanceData = localStorage.getItem("userData")
		if(instanceData !== null){
			userData = JSON.parse(instanceData) 	
			//linear search algorithm
			for(let i = 0; i < userData.length; i++){
				if(userData[i].usrName == usrName){
					showData(userData[i].usrName, userData[i].usrAge, userData[i].usrEmail)
				}
				else
				{
					alert("The user does not exist")
				}
			}
		}
	}
	function showData(name, age, email){
		let tbl = document.getElementById("viewData")
		let newRow = tbl.insertRow()
		let cell1 = newRow.insertCell(0)
		let cell2 = newRow.insertCell(1)
		let cell3 = newRow.insertCell(2)
		for(let i = 0; i < 1; i++){
			cell1.innerHTML = name
			cell2.innerHTML = age
			cell3.innerHTML = email
		}
	}
````
### Testing
#### Input
Data validation in the search form is done using the following procedure
```html
	<div>
		<form>
			<input type="text" id="name" onchange="checkData()">
			<input type="number" id="age" onchange="checkData()>
			<input type="text" id="email" onchange="checkData()>
			<input type="submit" onclick="getItem()" onchange="checkData()>
		</form>
	</div>
```
```javascript
	function checkData(){
		//check length of name entered
		let usrName = document.getElementById("name").value 
		if(usrName.length > 20)
			alert("Name too long")
		else if(usrName.length < 1)
			alert("Name too short")
		else
			usrName.style.backgroundColor = "green"
		//check if the user is 18 or older
		let usrAge = document.getElementById("age").value 
		if(usrName < 18)
			alert("This website is for 18 years or older")
		else
			usrName.style.backgroundColor = "green"
		//check if a valid email is entered
		let usrEmail = document.getElementById("email").value 
		if(usrEmail.length < 4)
			alert("This email is invalid")
		else
			usrName.style.backgroundColor = "green"
	}
```
## Installation
### pulling from github repository
The end user can install myPorfolio from the github repository by following the procedure
```pip
	mkdir /home/silas/Downloads/myPortfolio
	cd /home/silas/Downloads/myPortfolio
	touch index.html styles.css README.md
	git pull https://github.com/greatsilas23/myPortfolio
```	
## Operation And Maintenance
### Online
myPortfolio can be viewed online by following the procedure 
```pip
	firefox https://greatsilas23.github.io/myPortfolio 
```
### Maintenance
myPortfolio can be maintained as it is open source by following the procedure
```pip
	git remote remove origin
	git remote add origin https://github.com/greatsilas23/myPortfolio
	git commit -m "Maintainance"
	git push origin main
```
### Local
myPortfolio can be viewed locally by following the procedure
```pip
	firefox file:///home/silas/Downloads/myPortfolio
```
