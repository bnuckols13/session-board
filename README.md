# Session board

A one-page, self-contained session board for screen-sharing in individual sessions: agenda, feelings check-in, three activity cards, and a closing choice.

It holds no patient data. Everything typed stays in the browser tab (sessionStorage) and is gone when the tab closes. Nothing is sent anywhere.

The food quest card follows an exposure tracking sheet: a quest map of steps, a -10 to +10 thermometer with a personal green zone, and a log of each try (before, highest or lowest, end).

A setup link can prefill the quest story and steps through the URL fragment: `#q=` followed by base64url JSON `{"h": hero, "v": villain, "a": ally, "s": [up to 8 steps]}`. Browsers never send the fragment to the server, and the page removes it from the address bar after reading it.
