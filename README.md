# Subtle Loading State Bug in React with Async/Await

This repository demonstrates a subtle bug in a React component that uses the `useEffect` hook and `async/await` for data fetching. The bug involves improper handling of the loading state when an error occurs during the fetch operation.

## The Bug

The `MyComponent` component fetches data from an API endpoint.  If the fetch operation is successful, the data is displayed. If there's an error, an error message is shown.  However, there's a race condition where the loading state might not be updated correctly if the error is thrown.

## The Solution

The solution is using a `finally` block within the `useEffect` hook.  This ensures the `setLoading(false)` is always executed, regardless of whether the fetch operation succeeds or fails. This prevents the component from remaining in an indefinite loading state.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Observe the loading and error handling behaviour.  You can simulate errors by modifying the API endpoint or network conditions.
