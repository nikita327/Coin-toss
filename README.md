# Coin-toss
import random
def toss_coin():
    return "Heads" if random.choice([True, False]) else "Tails"
def coin_toss_session():
    while True:
        try:
            flips = int(input("Enter the number of coin tosses: "))
            if flips <= 0:
                print("Please enter a positive number.")
                continue
        except ValueError:
            print("Invalid input. Please enter a number.")
            continue
            
        heads = 0
        tails = 0

        for _ in range(flips):
            result = toss_coin()
            print(f"Toss result: {result}")
            if result == "Heads":
                heads += 1
            else:
                tails += 1

        print("\n--- Toss Summary ---")
        print(f"Heads: {heads} ({(heads / flips) * 100:.2f}%)")
        print(f"Tails: {tails} ({(tails / flips) * 100:.2f}%)")

        repeat = input("\nDo you want to toss again? (yes/no): ").strip().lower()
        if repeat not in ["yes", "y"]:
            print("Thanks for playing!")
            break


coin_toss_session()
