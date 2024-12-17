# React Router v6 Catch-All Route Bug

This repository demonstrates a subtle bug in React Router v6 related to the catch-all route ("/*") when navigating to a non-existent path.  The issue involves unexpected behavior when transitioning from a valid route to an invalid one; the catch-all route might not render as expected, instead showing the previous route's content.

## Steps to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Navigate to the `/` route (home). 
5. Try navigating to a non-existent route (e.g., `/invalid`).

The catch-all route should ideally render "404 Not Found". However, you might observe that the Home page or the previous page briefly remains visible before being replaced by the 404 page, or not at all.

## Solution

The solution involves using the `useLocation` hook to enforce a re-render when the route changes, ensuring the catch-all route is always rendered correctly for unmatched routes.  See the `AppSolution.js` file for the corrected implementation.