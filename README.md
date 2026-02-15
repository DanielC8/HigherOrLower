# Higher or Lower

A desktop gambling game built with Python and Tkinter. Players create accounts, place bets, and predict whether the next randomly generated number will be higher or lower than the current one. Longer winning streaks yield bigger payouts.

## Features

- **Account System**: Create accounts with validated credentials and log in across sessions.
- **Higher or Lower Game**: Place bets and predict whether the next number will be higher or lower. Winnings scale with streak length.
- **Leaderboard**: Top 10 players ranked by balance, displayed on the main screen and user menu.
- **Persistent Storage**: User data (credentials and balances) saved to disk via pickle between sessions.

## Project Structure

- **`main.py`**: All application logic -- GUI, authentication, game mechanics, leaderboard, and data persistence.
- **`passfile.txt`**: Binary pickle file storing user data (`{username: {password: balance}}`). Auto-created on first run.

## How It Works

1. **Splash Screen**: Presents options to create an account, log in, or exit. Shows the leaderboard.
2. **Account Creation**: Username must be unique. Password must be at least 8 characters with at least one digit and one lowercase letter.
3. **User Menu**: Displays current balance, a button to play, and the leaderboard.
4. **Gameplay**:
   - Player places a bet ($0 -- $10,000).
   - A number between 2--9 is generated.
   - Player guesses if the next number (1--10) will be higher or lower.
   - Correct guesses continue the round; wrong guess ends it.
   - Ties are re-rolled (the next number is never equal to the current one).
5. **Payouts**: Based on streak length:

   | Streak | Payout         |
   |--------|----------------|
   | 0--3   | $0 (lose bet)  |
   | 4      | 10% of bet     |
   | 5      | 40% of bet     |
   | 6      | 80% of bet     |
   | 7      | 130% of bet    |
   | 8      | 180% of bet    |
   | 9      | 250% of bet    |
   | 10     | 320% of bet    |
   | 11+    | Scales further |

## Usage

1. Install Python 3.10+.
2. Run the application:
   ```bash
   python3 main.py
   ```
3. Create an account or log in from the splash screen.
4. Place a bet and play. Close the window or click "Save and Exit" to quit.

## Requirements

- **Python 3.10+**
- **Tkinter** (included with most Python installations)
