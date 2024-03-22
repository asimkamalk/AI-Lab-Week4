
class TicTacToe:
    def __init__(self):
        # Initialize an empty board with 9 spaces
        self.board = [" " for _ in range(9)]
        # Start the game with player X
        self.current_player = "X"
        # Set the winner to None at the start of the game
        self.winner = None

    def display_board(self):
        # Display the current state of the board
        print("\nCurrent Board:")
        for row in [self.board[i:i + 3] for i in range(0, 9, 3)]:
            print(" | ".join(row))
            print("-" * 9)

    def make_move(self, position):
        # Make a move if the chosen position is empty
        if self.board[position] == " ":
            self.board[position] = self.current_player
            # Check for a winner after each move
            self.check_winner()
            # Switch turns between players
            self.current_player = "O" if self.current_player == "X" else "X"
        else:
            # Inform the player if the move is invalid
            print("Invalid move. Try again.")

    def check_winner(self):
        # Define all possible winning combinations
        winning_combinations = [
            (0, 1, 2), (3, 4, 5), (6, 7, 8),
            (0, 3, 6), (1, 4, 7), (2, 5, 8),
            (0, 4, 8), (2, 4, 6)
        ]

        for combo in winning_combinations:
            a, b, c = combo
            # Check if any winning combination is met
            if self.board[a] == self.board[b] == self.board[c] != " ":
                self.winner = self.board[a]
                return

        # Declare a tie if there are no empty spaces left and no winner
        if " " not in self.board:
            self.winner = "Tie"

    def play_game(self):
        # Main game loop
        while not self.winner:
            self.display_board()
            try:
                # Prompt the current player to enter a move
                position = int(input(f"{self.current_player}'s turn. Enter position (0-8): "))
                self.make_move(position)
            except ValueError:
                # Handle invalid input
                print("Invalid input. Please enter a number between 0 and 8.")

        # Display the final board and announce the result
        self.display_board()
        if self.winner == "Tie":
            print("It's a tie!")
        else:
            print(f"{self.winner} wins!")

# Start the game if this file is executed
if __name__ == "__main__":
    game = TicTacToe()
    game.play_game()
