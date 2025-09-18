---
layout: project
type: project
image: img/tictactoe.png
title: "TicTacToe"
date: 2025-09-17
published: true
labels:
  - Java
  - Swing
  - Game Development
summary: "A GUI-based Tic-Tac-Toe game created with Java Swing that allows two players to play, detects wins/ties, and saves results to a file."
---

This project implements the classic Tic-Tac-Toe game where two players take turns placing X and O on a 3x3 grid. The goal is to get three of the same symbol in a row, column, or diagonal.  

I used **Java Swing** to handle the game interface and logic, such as tracking the current player, checking for a win or draw, and saving the result to a file. The grid is built with `JButton`s, and an `ActionListener` responds to player clicks. I tested the game by playing multiple rounds to confirm that it correctly detects wins, ties, and switches turns.  

Here is a small snippet showing how the game responds to button clicks:

```java
@Override
public void actionPerformed(ActionEvent e) {
    if (gameOver) return;
    JButton clickedButton = (JButton) e.getSource();
    if (!clickedButton.getText().equals("")) return;

    clickedButton.setText(String.valueOf(currentPlayer));

    if (checkForWin()) {
        statusLabel.setText("Player " + currentPlayer + " wins!");
        gameOver = true;
        saveGameResult(currentPlayer + " wins!");
    } else if (isBoardFull()) {
        statusLabel.setText("It's a tie!");
        gameOver = true;
        saveGameResult("It's a tie!");
    } else {
        currentPlayer = (currentPlayer == 'X') ? 'O' : 'X';
        statusLabel.setText("Player " + currentPlayer + "'s turn");
    }
}
