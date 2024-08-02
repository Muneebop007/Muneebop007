import random

# Define card values and suits
values = ["2", "3", "4", "5", "6", "7", "8", "9", "10", "J", "Q", "K", "A"]
suits = ["Hearts", "Diamonds", "Clubs", "Spades"]

# Create a deck of cards
deck = [value + " of " + suit for value in values for suit in suits]

# Shuffle the deck
random.shuffle(deck)

# Deal three cards to each player
def deal_cards():
    return [deck.pop() for _ in range(3)]

# Determine the rank of a hand (basic ranking: high card, pair, etc.)
def rank_hand(hand):
    values_in_hand = [card.split(" ")[0] for card in hand]
    suits_in_hand = [card.split(" ")[-1] for card in hand]
    
    if len(set(suits_in_hand)) == 1:  # Flush
        return 5, values_in_hand
    elif len(set(values_in_hand)) == 1:  # Three of a kind
        return 4, values_in_hand
    elif len(set(values_in_hand)) == 2:  # Pair
        return 3, values_in_hand
    else:  # High card
        return 2, values_in_hand

# Compare two hands
def compare_hands(hand1, hand2):
    rank1, values1 = rank_hand(hand1)
    rank2, values2 = rank_hand(hand2)
    
    if rank1 != rank2:
        return "Hand 1 wins" if rank1 > rank2 else "Hand 2 wins"
    
    # If ranks are the same, compare values (simple comparison for now)
    sorted_values1 = sorted(values1, key=lambda x: values.index(x), reverse=True)
    sorted_values2 = sorted(values2, key=lambda x: values.index(x), reverse=True)
    
    for v1, v2 in zip(sorted_values1, sorted_values2):
        if values.index(v1) != values.index(v2):
            return "Hand 1 wins" if values.index(v1) > values.index(v2) else "Hand 2 wins"
    
    return "It's a tie!"

# Main game loop
def main():
    print("Welcome to 3 Patti!")
    
    player1_hand = deal_cards()
    player2_hand = deal_cards()
    
    print("Player 1's hand:", player1_hand)
    print("Player 2's hand:", player2_hand)
    
    result = compare_hands(player1_hand, player2_hand)
    print(result)

if __name__ == "__main__":
    main()
