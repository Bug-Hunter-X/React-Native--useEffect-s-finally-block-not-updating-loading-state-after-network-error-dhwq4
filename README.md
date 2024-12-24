# React Native: useEffect's finally block not updating loading state after network error

This repository demonstrates a common error in React Native applications where the loading state is not properly updated after a network request fails within a `useEffect` hook's `finally` block.  The issue lies in the improper handling of asynchronous operations and the timing of state updates.

The `bug.js` file contains the buggy code, which shows an `useEffect` hook attempting to fetch data from an API. If the API request fails, the error is caught, but the `loading` state doesn't update because of the asynchronous nature of the `setLoading` function within the `finally` block.  This results in the UI remaining stuck in the loading state indefinitely.

The `bugSolution.js` file provides the corrected code, resolving this issue by ensuring the `setLoading(false)` function is executed properly even if there is a network error.