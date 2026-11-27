# ARIN121 Assignment 3: Travel Planner

An AI travel planning assistant written as a system prompt (`system-prompt.md`) for Google AI Studio. It helps travellers decide where to go and then build a day-by-day itinerary.

This version extends my Assignment 2 planner with an activity menu and a new multi-turn activity, Choose Between Destinations. The original Assignment 2 prompt is kept in the commit history ("Preserve Assignment 2 starting prompt").

## What the planner can do

### Activity menu (new)

If you open with a general message such as "Hi, can you help me with a trip?", the planner shows a menu with two activities:

1. **Plan a trip**
2. **Choose between destinations**

You can pick an activity by typing its number, its name, or just saying what you need in your own words (for example, "Should I go to Lisbon or Barcelona?"). If your first message already makes the activity clear, the planner skips the menu and starts it.

You can switch activities at any point, even halfway through. The planner confirms the switch, repeats the details it is keeping (destinations, trip length, dates, who is travelling, budget, interests) in one sentence, and does not ask for them again. Type "menu" at any time to see the menu again.

### Choose Between Destinations (new)

For when you are deciding between two or three places. The planner asks one question at a time and waits for your answer before moving on:

1. Which destinations you are considering.
2. How long the trip is and roughly when you are going.
3. The two or three things that matter most to you (for example cost, food, beaches, weather, getting around without a car). If you already said this earlier, it uses what you said instead of asking again.

It then shows a short comparison table with one row per priority, gives an initial recommendation with its main trade-off, and asks if anything still worries you. Your answer is used to refine the recommendation (at most twice). The activity ends with a final recommendation and an offer to plan the trip to that destination using everything you have already told it. Say "just pick one" to get a recommendation straight away.

### Plan a Trip (from Assignment 2)

- **Preference questions:** asks one short round of questions about who is travelling, budget, interests and pace before planning.
- **Day logistics:** each day is grouped by neighbourhood, with approximate travel times between activities and an indoor "Plan B".
- **Targeted revisions:** changes only the part of the itinerary you ask about and summarizes what changed.
- **Ambiguous destinations:** asks which place you mean for names like Kingston or London (this now applies to both activities).
- **Guardrails:** stays on travel topics and does not present prices, opening hours or news as confirmed.

## How to use it

1. Open Google AI Studio Playground (tested with Gemini 3.5 Flash Lite, thinking level Minimal, default settings).
2. Paste the contents of `system-prompt.md` into **System instructions**.
3. Start a new chat with a general message to see the menu, or ask for an activity directly.

## Files

- `system-prompt.md`: the complete system prompt.
- `README.md`: this file.
