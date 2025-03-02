

 Overview
This project is a comprehensive simulation of the Blackjack game integrated with Artificial Intelligence components, including Markov Decision Processes (MDP) and Deep Q-Networks (DQN). The objective of this project is to provide an interactive and strategic Blackjack experience, enhanced by real-time decision recommendations for players.

 Features
Deck Management: A six-deck shoe with shuffling and auto-reset when the deck is low.
Player and Dealer Logic: Implements standard Blackjack rules for players and the dealer.
Strategy Engine: Utilizes Markov Decision Process (MDP) for improved Blackjack strategy.
Deep Q-Network (DQN): Reinforcement learning for dynamic decision-making.
Real-Time Decision Recommendation: Combines MDP and DQN for optimized player actions.
Multiple Actions: Supports all standard Blackjack actions: Hit, Stand, Double Down, Split, and Surrender.
Multi-Player Support: Allows multiple players to compete against the dealer.

## Modules Overview

### 1. Deck Management (Deck Class)
This module handles the deck creation, shuffling, and card drawing process.
- Methods:
  - create_deck(): Generates a standard 52-card deck.
  - shuffle(): Shuffles the deck using Python's built-in random.shuffle().
  - draw_card(): Draws a card from the deck. Reshuffles when the deck is low.

### 2. Player Class (Player)
Represents a player in the game with attributes like name, hand, score, and available actions.
- Attributes:
  - name: Name of the player.
  - hand: List of cards in the player's hand.
  - score: Calculated score of the hand.
  - actions: List of possible actions (Hit, Stand, Double Down, Split, Surrender).
- Methods:
  - receive_card(card): Adds a card to the hand and recalculates the score.
  - calculate_score(): Calculates the hand's score, treating Aces as 1 or 11 as needed.

### 3. Dealer Class (Dealer)
Inherits from Player and represents the dealer in the game.
- Methods:
  - play(deck): Implements the dealer's strategy of hitting until reaching a score of 17 or higher.

### 4. Markov Decision Process (MDP)
Implements an improved Blackjack strategy using Markov Decision Processes.
- Attributes:
  - states: Possible scores from 4 to 21.
  - actions: Available actions (Hit, Stand, etc.).
  - policy: A predefined policy for each state using optimal Blackjack strategy.
- Methods:
  - recommend_action(state, player_hand): Recommends the best action based on the player's state and hand.

### 5. Deep Q-Network (DQN)
A Reinforcement Learning model using TensorFlow for dynamic decision-making.
- Attributes:
  - state_size: Input size representing the state.
  - action_size: Output size representing possible actions.
  - memory: Replay memory for experience replay.
  - gamma: Discount rate for future rewards.
  - epsilon: Exploration rate for action selection.
  - epsilon_decay and epsilon_min: Control exploration-exploitation trade-off.
  - learning_rate: Learning rate for model training.
- Methods:
  - build_model(): Builds a neural network with two hidden layers using TensorFlow.
  - recommend_action(state): Recommends an action using an ε-greedy policy.

### 6. Real-Time Decision Maker (DecisionMaker)
Combines MDP and DQN recommendations to provide real-time decisions.
- Methods:
  - recommend(state, player_hand): Chooses the best action based on both MDP and DQN logic.

### 7. Main Game Loop (main() Function)
Handles the game flow, including:
- Initializing the deck, players, and dealer.
- Dealing initial hands to players and the dealer.
- Displaying player and dealer hands.
- Recommending actions using the DecisionMaker module.
- Accepting player input for actions.
- Managing dealer actions and determining the result.

## Requirements
- Python 3.x
- Required libraries:
  - random - For shuffling the deck and random choices.
  - numpy - For numerical operations.
  - tensorflow - For building and training the DQN model.
  - collections.deque - For experience replay memory.



