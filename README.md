# Expo Linking API: `addEventListener` Inconsistency

This repository demonstrates a bug where the Expo `Linking.addEventListener` function intermittently fails to trigger when handling deep links. This can lead to unpredictable behavior and prevent your application from responding to incoming URLs correctly. The issue is more prevalent in production environments and might be related to background processes or specific device configurations.

The `bug.js` file contains code that showcases the problem. The `bugSolution.js` provides a workaround that improves reliability.

## Reproduction

1. Clone this repository.
2. Run `expo start`.
3. Try opening a deep link in your browser or device that should trigger an event handled by `Linking.addEventListener`.
4. Observe that the event handler does not always fire consistently, indicating the bug's presence.

## Workaround

The `bugSolution.js` file implements a workaround that adds a `Linking.getInitialURL()` check on app start. This is done to capture any initial deep link that might have been missed by `addEventListener`. This provides a more robust solution for deep link handling.