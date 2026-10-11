# What's on Flowers: AI Customer Service Chatbot

A no-code chatbot for a fictional flower shop, built with IBM watsonx Assistant and embedded in a WordPress site.

- **Live demo:** <https://flowers1.wordbox.intela.io/arczxy/> (hosted in a lab environment, so the link may stop working; see the screenshots below)
- **Course:** IBM, Building AI Powered Chatbots Without Programming (Coursera)
- **Certificate:** <https://coursera.org/verify/CL6E7FV8X9S0>

## Screenshots

![Conversation test 1](Test%20Case%201.png)

![Conversation test 2](Test%20Case%202.png)

![Conversation test 3](Test%20Case%203.png)

## What it does

- Finds store locations and opening hours for five Canadian cities
- Remembers the selected city, so "What are its hours?" needs no repeat question
- Recommends bouquets by occasion, with a "someone special?" follow-up and images
- Answers delivery questions (in-store pickup only) and handles thank-you and goodbye messages
- Handles unclear input with a friendly fallback and a phone number for human help

## How it's built

- **11 actions:** Greet customer, Greetings, Location information, Hours of operation, Flower recommendations, Delivery, Thank you, Goodbye, No matches, Fallback, Trigger word detected
- Session variables (city, occasion) carry context across actions
- Conditional steps and variation replies keep answers relevant and varied
- Web chat embedded through the watsonx Assistant WordPress plugin

## Testing

Ran a 9-step scripted conversation plus edge cases: typos, typed instead of clicked answers, out-of-scope questions, gibberish, and requests for a human. Full results, including the bugs found and fixed, are in [test-cases.md](test-cases.md).

## Repository contents

| File | Description |
|---|---|
| `whats-on-flowers-actions.json` | Exported watsonx Assistant actions |
| `test-cases.md` | Test script, results and fixes |
| `Test Case 1.png` to `Test Case 3.png` | Conversation screenshots |

## Known limitations

- No live-agent handoff; the bot points users to the shop phone number
- Delivery is not supported
- The built-in trigger-word action (danger or profanity words) still uses IBM's default settings
- Site footer and product dates come from the lab template

## Credits and note

Bouquet images are provided by the IBM course materials. The shop, addresses and phone numbers are fictional.

Built by Saheed Ayorinde
