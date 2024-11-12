# React Date Proposal Button Game

This is a playful React project that presents the question: **"Will you go on a date with me?"** with two options: **"Yes"** and **"No."** When the user tries to click **"No,"** the button moves to a random position on the screen, making it hard to reject the proposal. If the user clicks **"Yes,"** a custom message is displayed, adding to the fun!

## Features

- **Interactive Button Behavior**: The "No" button relocates on hover, giving a humorous challenge.
- **Dynamic Feedback**: Clicking "Yes" displays a custom response for a delightful user experience.
- **React-Based Architecture**: The project leverages React for handling UI components and state management.

## Technologies Used

- **React**: To build the UI and manage component state.
- **CSS**: For styling the components and positioning elements.
- **JavaScript**: Adds interactivity and logic to button behavior.

## How It Works

1. **Render Question and Buttons**: The question "Will you go on a date with me?" appears along with "Yes" and "No" buttons.
2. **Button Logic**:
   - **"No" Button**: The `onMouseEnter` event triggers a function that repositions the button randomly on the screen.
   - **"Yes" Button**: The `onClick` event displays a personalized or fun message in the UI.

## Example Code

Below is a sample of the React code used to implement the button interactions:

```javascript
import React, { useState } from "react";

function DateProposal() {
    const [message, setMessage] = useState("");

    const moveNoButton = (e) => {
        e.target.style.position = "absolute";
        e.target.style.top = `${Math.random() * window.innerHeight}px`;
        e.target.style.left = `${Math.random() * window.innerWidth}px`;
    };

    const handleYesClick = () => {
        setMessage("Yay! Let's go on that date!");
    };

    return (
        <div className="App">
            <h1>Will you go on a date with me?</h1>
            <button onClick={handleYesClick}>Yes</button>
            <button onMouseEnter={moveNoButton}>No</button>
            {message && <p>{message}</p>}
        </div>
    );
}

export default DateProposal;
