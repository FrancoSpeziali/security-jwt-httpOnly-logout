# Handling user logged in status with React's Context API

This assignment will allow you to experience handling the login status of the user with JWT httpOnly cookies

> Difficulty level: Intermediate 🥸🏁

## Keywords

`react`, `Context API`, `express`, `mongoose`, `bcrypt`, `passport`, `passport-jwt`, `jsonwebtoken`, `jwt`, `sessionStorage`

## What you will be doing

For this assignment you will have to:

1. Re-use the code from `security-jwt-httpOnly`
2. Setup Context API in the application
3. Store the logged in state in localStorage / Context API

## Getting Started

For this assignment, you will be re-using the cod from the assignment `security-jwt-httpOnly`

## Tasks

## Task 1 - (Frontend) Setting up Context API

1. Setup a Context API storage in the root of the application 

We will use this Context API to store the logged in status

> Hint: We will store this state as a boolean value

## Task 2 - (Frontend) Setting the logged in status

In the frontend Login component;

1. If the login is a success, set the logged in status to true in your Context API
2. Additionally, store this state in the localStorage

## Task 3 - (Frontend) Navigation

Add a menu to the frontend which includes links to all available pages

> Hint: You can use the `Link` component from `react-router-dom`

## Task 4 - (Backend) - Logout

Since we can't modify or delete our JWT httpOnly cookie, we must call our backend, telling it to remove the cookie for us. We will create a new endpoint to do this.

1. Under the `/user` route, add a new endpoint which matches the path `/logout`
2. Write some controller logic for this new endpoint
3. The controller should use the response method `clearCookie`

> Hint: clearCookie accepts 2 values, the name of the cookie, and the options we used to define the cookie. For example;
> ```javascript
> response.clearCookie("jwt", {
>   httpOnly: true,
>   secure: false,
>   sameSite: "lax",
> })
> ```

## Task 5 - (Frontend) - Logout route and component

We want the user to be able to logout from our application from the GUI in the frontend

1. Create a new component `Logout`
2. Add a new menu item `Logout`, which points to the path `/logout`, and also points to the `Logout` component

## Task 6 - (Frontend) - Logout component logic

Our Logout component should be responsible for logging out the user. This entails a number of tasks, and so we would like to store this logic in a central place (the Logout component).

Modify the logic of the component to;

1. Call the `/logout` endpoint you created in **Task 5**
2. Change the logout status of the user in your Context API from **true** to **false**
3. Redirect the user from the logout page to the login page
    > Hint: You can use the `useNavigate` hook from `react-router-dom` (v6)

## Task 7 - Test everything!
