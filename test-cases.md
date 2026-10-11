# Test Cases: What's on Flowers Chatbot

Manual testing of the IBM watsonx Assistant chatbot, run in the Preview panel
and again on the live WordPress site after publishing.

**Result key:** Pass = worked as expected · Fixed = failed first, fixed, then passed · Not tested = not run yet

## 1. Main conversation script

| # | User input | Expected result | Result |
|---|---|---|---|
| 1 | Hello | Greeting message | Pass |
| 2 | Where are your stores? | City list with 5 buttons | Pass |
| 3 | Toronto | Toronto address and phone number | Pass |
| 4 | What are its hours? | Toronto hours, without asking for the city again | Pass |
| 5 | I want to gift some flowers | Occasion buttons | Pass |
| 6 | Thank You (occasion) | "Is this gift for someone special?" | Pass |
| 7 | Yes | Bouquet recommendation with image | Pass |
| 8 | Thank you | One reply only | Fixed |
| 9 | Bye | Goodbye mentioning the Toronto store | Fixed |

**Fixes made:**
- Step 8: a plain-text line and a variation block repeated the same reply. Removed the duplicate.
- Step 9: corrected a capitalization typo and added a fallback step for users who never chose a city.
- Several replies displayed in a grey code box because the text was wrapped in triple backticks. Removed them.

## 2. Other conversation paths

| User input | Expected result | Result |
|---|---|---|
| Hello, then Bye (no city chosen) | "...at one of our stores soon!" | Pass |
| Gift, Thank You, No | Graceful Appreciation reply | Pass |
| Gift, Birthday, Yes | One Birthday reply, then the action ends | Fixed |
| Gift, Anniversary | Recommendation from the standard occasions list | Pass |
| Stores, Vancouver, then hours | Vancouver address, then Vancouver hours | tested |
| Gift, Other / Just Because, Yes and No | Just For Her and Happy Blossoms replies | tested |

**Fixes made:**
- Birthday, Yes: the step continued into the next step. Changed it to end the action.

## 3. Messy and out-of-scope input

| User input | Expected result | Result |
|---|---|---|
| wat time do u open | Understands the typos and asks for a city | Pass |
| toronto (typed, not clicked) | Matches the city and gives the hours | Pass |
| Do you deliver to Lagos? | Explains delivery is not available | Fixed |
| asdfgh | Friendly fallback message | Fixed |
| Can I speak to a human? | Phone number for the shop | Fixed |
| birthday flowers for my mum | Recognizes the gifting intent | tested |

**Fixes made:**
- Lagos question: the bot replied with the Toronto address. Added a Delivery action with example phrases.
- asdfgh: replaced the generic "I'm afraid I don't understand" message with one that lists what the bot can help with.
- Human request: the default fallback tried to connect to a live agent that does not exist. Replaced with a message pointing to the shop phone number, and changed every step to end the action.

## 4. Known limitations

- No live-agent handoff.
- Delivery is not supported.
- Typed city names work, but misspelled city names have not been tested.
- The shop, addresses and phone numbers are fictional.
