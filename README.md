# goit-js-hw-05

## Description

Homework for Topic 8: Array Iterating Methods. Practice using `map()`, `filter()`, `toSorted()`, `reduce()`, and method
chaining.

## Project Structure

```
goit-js-hw-05/
├── js/
│   ├── task-1.js
│   ├── task-2.js
│   ├── task-3.js
│   └── task-4.js
├── .gitignore
├── .prettierrc.json
├── index.html
└── README.md
```

## How to Run

Open `index.html` in the browser and check the DevTools console for output.

## Tasks

### Task 1 — User Names

**File:** `task-1.js`

Write an arrow function `getUserNames(users)` that takes one parameter `users` — an array of user objects. The function
should return an array of all user names (the `name` property) from the `users` array.

```js
console.log(
  getUserNames([
    { name: 'Moore Hensley', email: 'moorehensley@indexia.com', balance: 2811 },
    { name: 'Sharlene Bush', email: 'sharlenebush@tubesys.com', balance: 3821 },
    { name: 'Ross Vazquez', email: 'rossvazquez@xinware.com', balance: 3793 },
    { name: 'Elma Head', email: 'elmahead@omatom.com', balance: 2278 },
    { name: 'Carey Barr', email: 'careybarr@nurali.com', balance: 3951 },
    { name: 'Blackburn Dotson', email: 'blackburndotson@furnigeer.com', balance: 1498 },
    { name: 'Sheree Anthony', email: 'shereeanthony@kog.com', balance: 2764 },
  ])
);
// ["Moore Hensley", "Sharlene Bush", "Ross Vazquez", "Elma Head", "Carey Barr", "Blackburn Dotson", "Sheree Anthony"]
```

**Mentor checklist:**

- Variable `getUserNames` is declared
- `getUserNames` is assigned an arrow function with parameter `(users)`
- The `map()` method is used to iterate over the `users` parameter
- Calling the function with the specified array of users returns
  `["Moore Hensley", "Sharlene Bush", "Ross Vazquez", "Elma Head", "Carey Barr", "Blackburn Dotson", "Sheree Anthony"]`
- Calling the function with random but valid arguments returns the correct value

---

### Task 2 — Users With a Friend

**File:** `task-2.js`

Write an arrow function `getUsersWithFriend(users, friendName)` that takes two parameters:

- `users` — an array of user objects
- `friendName` — the name of a friend to search for

The function should return an array of all users from the `users` array who have a friend named `friendName`. Each
user's friends are stored in the `friends` property. If no users have such a friend, the function should return an empty
array.

**Tips:**

- The `filter()` method can be used to create a new array with elements that satisfy a certain condition.
- Use the `includes()` method to check whether the `friends` array contains `friendName`.

```js
const allUsers = [
  { name: 'Moore Hensley', friends: ['Sharron Pace'] },
  { name: 'Sharlene Bush', friends: ['Briana Decker', 'Sharron Pace'] },
  { name: 'Ross Vazquez', friends: ['Marilyn Mcintosh', 'Padilla Garrison', 'Naomi Buckner'] },
  { name: 'Elma Head', friends: ['Goldie Gentry', 'Aisha Tran'] },
  { name: 'Carey Barr', friends: ['Jordan Sampson', 'Eddie Strong'] },
  { name: 'Blackburn Dotson', friends: ['Jacklyn Lucas', 'Linda Chapman'] },
  { name: 'Sheree Anthony', friends: ['Goldie Gentry', 'Briana Decker'] },
];

console.log(getUsersWithFriend(allUsers, 'Briana Decker'));
// [
//   { name: "Sharlene Bush", friends: ["Briana Decker", "Sharron Pace"] },
//   { name: "Sheree Anthony", friends: ["Goldie Gentry", "Briana Decker"] },
// ]

console.log(getUsersWithFriend(allUsers, 'Goldie Gentry'));
// [
//   { name: "Elma Head", friends: ["Goldie Gentry", "Aisha Tran"] },
//   { name: "Sheree Anthony", friends: ["Goldie Gentry", "Briana Decker"] },
// ]

console.log(getUsersWithFriend(allUsers, 'Adrian Cross')); // []
```

**Mentor checklist:**

- Variable `getUsersWithFriend` is declared
- `getUsersWithFriend` is assigned an arrow function with parameters `(users, friendName)`
- The `filter()` method is used to iterate over the `users` parameter
- If `friendName` is `"Briana Decker"`, the function returns an array of user objects with names Sharlene Bush and
  Sheree Anthony
- If `friendName` is `"Goldie Gentry"`, the function returns an array of user objects with names Elma Head and Sheree
  Anthony
- If `friendName` is `"Adrian Cross"`, the function returns an empty array
- Calling the function with random but valid arguments returns the correct value

---

### Task 3 — Sort by Friend Count

**File:** `task-3.js`

Write an arrow function `sortByDescendingFriendCount(users)` that takes one parameter `users` — an array of user
objects.

The function should return an array of all users sorted in descending order by the number of their friends (the
`friends` property).

```js
console.log(
  sortByDescendingFriendCount([
    { name: 'Moore Hensley', friends: ['Sharron Pace'], gender: 'male' },
    { name: 'Sharlene Bush', friends: ['Briana Decker', 'Sharron Pace'], gender: 'female' },
    { name: 'Ross Vazquez', friends: ['Marilyn Mcintosh', 'Padilla Garrison', 'Naomi Buckner'], gender: 'male' },
    { name: 'Elma Head', friends: ['Goldie Gentry', 'Aisha Tran'], gender: 'female' },
    { name: 'Carey Barr', friends: ['Jordan Sampson', 'Eddie Strong'], gender: 'male' },
    { name: 'Blackburn Dotson', friends: ['Jacklyn Lucas', 'Linda Chapman'], gender: 'male' },
    { name: 'Sheree Anthony', friends: ['Goldie Gentry', 'Briana Decker'], gender: 'female' },
  ])
);
// [
//   { name: "Ross Vazquez", friends: ["Marilyn Mcintosh", "Padilla Garrison", "Naomi Buckner"], gender: "male" },
//   { name: "Sharlene Bush", friends: ["Briana Decker", "Sharron Pace"], gender: "female" },
//   { name: "Elma Head", friends: ["Goldie Gentry", "Aisha Tran"], gender: "female" },
//   { name: "Carey Barr", friends: ["Jordan Sampson", "Eddie Strong"], gender: "male" },
//   { name: "Blackburn Dotson", friends: ["Jacklyn Lucas", "Linda Chapman"], gender: "male" },
//   { name: "Sheree Anthony", friends: ["Goldie Gentry", "Briana Decker"], gender: "female" },
//   { name: "Moore Hensley", friends: ["Sharron Pace"], gender: "male" },
// ]
```

**Mentor checklist:**

- Variable `sortByDescendingFriendCount` is declared
- `sortByDescendingFriendCount` is assigned an arrow function with parameter `(users)`
- The `toSorted()` method is used to iterate over the `users` parameter
- Calling the function with the specified `users` array returns a new array of users sorted in descending order by their
  friend count
- Calling the function with random but valid arguments returns the correct value

---

### Task 4 — Total Balance

**File:** `task-4.js`

Write an arrow function `getTotalBalanceByGender(users, gender)` that takes two parameters:

- `users` — an array of user objects
- `gender` — a string representing the gender

The function should use method chaining and return the total balance (the `balance` property) of users whose gender (the
`gender` property) matches the `gender` parameter value.

```js
const clients = [
  { name: 'Moore Hensley', gender: 'male', balance: 2811 },
  { name: 'Sharlene Bush', gender: 'female', balance: 3821 },
  { name: 'Ross Vazquez', gender: 'male', balance: 3793 },
  { name: 'Elma Head', gender: 'female', balance: 2278 },
  { name: 'Carey Barr', gender: 'male', balance: 3951 },
  { name: 'Blackburn Dotson', gender: 'male', balance: 1498 },
  { name: 'Sheree Anthony', gender: 'female', balance: 2764 },
];

console.log(getTotalBalanceByGender(clients, 'male')); // 12053
console.log(getTotalBalanceByGender(clients, 'female')); // 8863
```

**Mentor checklist:**

- Variable `getTotalBalanceByGender` is declared
- `getTotalBalanceByGender` is assigned an arrow function with parameters `(users, gender)`
- Method chaining is used in the correct order inside the function body
- The value of the `users` parameter is not mutated
- If `gender` is `"male"`, the function returns `12053`
- If `gender` is `"female"`, the function returns `8863`
- Calling the function with random but valid arguments returns the correct value

---

## Submission

- Link to the repository with source files
- Link to the live page on GitHub Pages
- Attached repository file in `.zip` format

## Requirements

- Code formatted with Prettier
- No errors or warnings in the browser console
- Project structure must match the specified schema exactly
