---
title: "Forms"
draft: false
arguments: []
weight: 3
---

```html
<form action="process.php" method="POST"> <!--action and method attribute are server-side thing-->
	<div> <!--used to place the elements on different lines-->
		<label>First Name</label>
		<input type="text" name="firstName" placeholder="Enter first name">
	</div>
	<br> <!--line breaker-don’t use, use CSS-->
	<div>
		<label>Last Name</label>
		<input type="text" name="lastName">
	</div>
	<br>
	<div>
		<label>Email</label>
		<input type="email" name="email">
	</div>
	<br>
	<div>
		<label>Message</label>
		<textarea name="message"></textarea> <!--textarea is a bigger input region for longer text-->
	</div>
	<br>
	<div>
		<label>Gender</label>
		<select name="gender">
		<option value="male">Male</option> <option value="female">Female</option>
		<option value="other">Other</option>
		</select> <!--select is used for selection between different options-->
	</div>
	<br>
	<div>
		<label>Age:</label>
		<input type="number" name="age" value="30">
	</div>
	<br>
	<div>
		<label>Birthday:</label>
		<input type="date" name="birthday">
	</div>
	<br>
	<input type="submit" name="submit" value="Submit">
</form>
```
