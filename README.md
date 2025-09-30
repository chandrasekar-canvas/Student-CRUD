# Student-CRUD
Thank you for Visiting my Projects
student-crud/
│── admin.html
│── user.html

When admin first opens page:

let students = JSON.parse(localStorage.getItem("students")) || [];

If no data → students = [] (empty array).

If already some data → load from localStorage.

When admin adds new student:

students.push({ roll, name });


push() adds the new student to the end of the array, it doesn’t replace old data.

Example:

First time: [ { roll: "101", name: "Ram" } ]

Next add: [ { roll: "101", name: "Ram" }, { roll: "102", name: "Sita" } ]

Then we save back to localStorage:

localStorage.setItem("students", JSON.stringify(students));


Now the whole array is stored as JSON text inside browser storage.

So when you refresh, or open user page, the same list is there.


On user side:

let students = JSON.parse(localStorage.getItem("students")) || [];


User reads the same students list → so whatever admin added is visible.

Admin adds "101 - Ram"
→ students = [{ roll:"101", name:"Ram" }]

Admin adds "102 - Sita"
→ students = [{ roll:"101", name:"Ram" }, { roll:"102", name:"Sita" }]

User page loads → sees both Ram and Sita
