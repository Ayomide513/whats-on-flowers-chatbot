# What's on Flowers: AI Customer Service Chatbot

A no-code chatbot for a fictional flower shop, built with IBM watsonx
Assistant and embedded in a WordPress site.

**Live demo:** https://flowers1.wordbox.intela.io/arczxy/
**Course:** IBM, Building AI Powered Chatbots Without Programming (Coursera)
**Certificate:** https://coursera.org/verify/CL6E7FV8X9S0

## What it does
- Finds store locations and opening hours for five Canadian cities
- Remembers the selected city, so "What are its hours?" needs no repeat question
- Recommends bouquets by occasion, with a "someone special?" follow-up and images
- Answers delivery questions (in-store pickup only) and thank-you or goodbye messages
- Handles unclear input with a friendly fallback and a phone number for human help

## How it's built
- Actions: Greet customer, Greetings, Location information, Hours of operation,
  Flower recommendations, Delivery, Thank you, Goodbye, No matches, Fallback
- Session variables (city, occasion) carry context across actions
- Conditional steps and variation replies keep answers relevant and varied
- Web chat embedded through the watsonx Assistant WordPress plugin

## Testing
Ran a 9-step scripted conversation plus edge cases: typos, typed instead
of clicked answers, out-of-scope questions, gibberish, and requests for a human.

## Known limitations
- No live-agent handoff; the bot points users to the shop phone number
- Delivery is not supported
- Site footer and product dates come from the lab template

## Note
The shop, addresses and phone numbers are fictional.

Built by Saheed Ayorinde
