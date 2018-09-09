# Mini Budget App v1.0
Built a mini monthly budget control app with a clean and nice interface.

## Code Structures
```
var budgetController = (function() {
	var Expense = function(id, description, value) {
		this.id = id;
		this.description = description;
		this.value = value;
		this.percentage = -1;
	}

	Expense.prototype.calcPercentage =  function(totalIncome) {
		if(totalIncome > 0) {
			this.percentage = Math.round((this.value / totalIncome) * 100 );
		}else {
			this.percentage = -1;
		}
	};

	Expense.prototype.getPercentage = function() {
		return this.percentage;
	}
	...
```
```
...
var controller = (function(budgetCtrl, UICtrl){

	var setupEventListeners = function() {
		var DOM = UICtrl.getDomstrings();
		document.querySelector(DOM.inputBtn).addEventListener("click", ctrlAddItem);
		document.addEventListener("keypress", function(event) {

	if (event.keyCode === 13 || event.which === 13) { // event.which for old browsers
		ctrlAddItem();
	}
});
		document.querySelector(DOM.container).addEventListener("click", ctrlDeleteItem);
		document.querySelector(DOM.inputType).addEventListener("change", UICtrl.changeType);
	};
```

## Technologies
- HTML5
- CSS3
- JavaScript

The app was written intentionally in only **vanilla and old(ES5)** Javascript with **structured** design patterns. No framework or library was used.

## Demo
**Live:** [Mini Budget](https://anilgunay.com/mini-budget)