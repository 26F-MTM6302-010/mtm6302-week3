# Adopt a Tiny Monster
## MTM6302 · Week 3 JavaScript Demo

Meet **Mochi**, your new study buddy. Mochi enjoys snacks, gets sleepy, and occasionally has enough energy to cause chaos.

Your mission is to bring this tiny monster to life using JavaScript. You’ll give it a name, feed it, play with it, and make its appearance respond to its energy.

The HTML and CSS are ready. You’ll build the behaviour.

## Your mission

By the end of this demo, you’ll be able to:

- Change your monster’s name and favourite snacks.
- Update its portrait, mood, and message.
- Feed it to increase its energy.
- Play with it to decrease its energy.
- Reveal its adoption certificate and toggle party mode.
- Reset its name, energy, and adoption status.

We’ll use the **browser console as our control panel**. Later in the course, we can connect these same actions to buttons.

## Get ready

1. Fork this repository and clone it to your computer.
2. Open your repository in Visual Studio Code.
3. Open `index.html` in Chrome.
4. Open the browser console:
   - **Mac:** Option + Command + J
   - **Windows:** Ctrl + Shift + J
5. Open `script.js` in your editor.

Write your JavaScript in `script.js`. Save and refresh the page after each change. Use the console to try functions once you have created them.

**Refreshing starts the game again.** Changes made during play are not saved.

## Plan before coding

### 1. Agree on the rules

Our monster has one main changing value: **energy**.

- It starts with **20 energy**.
- Feeding adds energy.
- Playing uses energy.
- Energy stays between **0 and 100**.

Its energy determines its mood:

| Energy | Mood |
|---|---|
| Below 30 | Sleepy |
| 30 to below 70 | Snack investigator |
| 70 to 100 | Ready for chaos |

The mood should agree with the portrait, message, and card styling.

### 2. Identify the parts we need

| Part | Responsibility |
|---|---|
| **HTML** | Provides the name, portrait, energy display, snack list, and certificate. |
| **CSS** | Defines how the page and each mood look. |
| **JavaScript state** | Remembers the current energy number. |
| **Decision function** | Chooses a mood from an energy value. |
| **Display function** | Updates the page to match the current energy. |
| **Action functions** | Feed, play, rename, adopt, celebrate, and reset. |

Our main interaction follows this sequence:

**Call an action → change energy → update the display**

Changing a number in JavaScript does not automatically change the page. We must tell the page what to display.

### 3. Find the page elements

Before changing an element, JavaScript needs a reference to it.

```text
FIND the monster's name
FIND the mood and energy displays
FIND the portrait and monster card
FIND the message
FIND the certificate and its name

FIND the snack list
MOVE to its first child
MOVE from that child to the next sibling
```

We’ll begin with small experiments: changing text, replacing a portrait, revealing the certificate, and adding or removing a CSS class.

### 4. Decide how to choose a mood

This function answers a question: **“What mood belongs to this energy value?”**

It returns an answer without changing the page.

```text
FUNCTION getMood(energyValue)

    IF energyValue is below 30
        RETURN "Sleepy"

    ELSE IF energyValue is below 70
        RETURN "Snack investigator"

    ELSE
        RETURN "Ready for chaos"
```

**Predict:** Which mood should we get at exactly 30? What about exactly 70?

### 5. Plan one display function

Several things must change together. Keeping those updates in one function helps us avoid a happy portrait with a sleepy message.

```text
FUNCTION updateMonster()

    ASK getMood for the mood matching the current energy

    UPDATE the mood text
    UPDATE the energy number

    REMOVE the previous mood classes

    IF energy is below 30
        APPLY sleepy styling
        SHOW the sleepy portrait
        UPDATE the portrait's alternative text
        SHOW a sleepy message

    ELSE IF energy is below 70
        APPLY hungry styling
        SHOW the hungry portrait
        UPDATE the portrait's alternative text
        SHOW a snack-related message

    ELSE
        APPLY happy styling
        SHOW the happy portrait
        UPDATE the portrait's alternative text
        SHOW an energetic message
```

Party styling is separate from mood styling. Feeding the monster should not cancel its party!

### 6. Plan the actions

Each energy action changes the number, keeps it within bounds, and refreshes the display.

```text
FUNCTION feedMonster(amount)

    ADD amount to energy
    LIMIT energy to the range 0–100
    CALL updateMonster()
```

```text
FUNCTION playMonster(amount)

    SUBTRACT amount from energy
    LIMIT energy to the range 0–100
    CALL updateMonster()
```

For this exercise, use whole-number amounts from **0 to 100**.

The other actions update specific parts of the page:

```text
FUNCTION renameMonster(newName)
    UPDATE the name on the monster card
    UPDATE the name on the certificate
    UPDATE the browser-tab title

FUNCTION adoptMonster()
    REMOVE the certificate's hidden attribute

FUNCTION toggleParty()
    TOGGLE the party styling on the monster card

FUNCTION resetMonster()
    SET energy to 20
    RENAME the monster "Mochi"
    REMOVE party styling
    HIDE the certificate
    CALL updateMonster()
```

### 7. Start the game

Defining a function teaches JavaScript an action. **Calling the function performs that action.**

```text
SET starting energy to 20

DEFINE our decision, display, and action functions

CALL renameMonster("Mochi")
CALL adoptMonster()
CALL updateMonster()
```

Once we’ve built the functions, we can try commands such as:

```js
renameMonster('Professor Pickles')
feedMonster(15)
playMonster(10)
toggleParty()
```

## How we’ll build it

We’ll work in small steps:

1. Find elements and change their text.
2. Explore the snack list.
3. Change attributes and CSS classes.
4. Use conditions to choose a mood.
5. Organize repeated work into functions.
6. Connect actions to the display.
7. Test and personalize the result.

At each step: **predict, code, observe, explain**.

## How will we know it works?

Start each test with `resetMonster()`.

| Action | Expected result |
|---|---|
| Feed 9 | Energy becomes 29: sleepy. |
| Feed 10 | Energy becomes 30: snack investigator. |
| Feed 50 | Energy becomes 70: ready for chaos. |
| Feed 100 | Energy stops at 100. |
| Play 100 | Energy stops at 0. |

Check the whole monster—not just the number. Its mood, portrait, alternative text, message, and styling should agree.

**Your first challenge:** Give your monster a name and a welcome message. What kind of study buddy have you adopted?
