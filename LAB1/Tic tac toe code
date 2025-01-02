import numpy as np
import random

flag = True
d = [["-"] * 3 for i in range(3)]
win = ""

def checkr(i):
    if d[i][0] == d[i][1] == d[i][2] != '-':
        global win
        win = d[i][0]
        return True
    return False

def checkc(i):
    if d[0][i] == d[1][i] == d[2][i] != '-':
        global win
        win = d[0][i]
        return True
    return False

def checkd():
    global win
    if d[0][0] == d[1][1] == d[2][2] != '-':
        win = d[0][0]
        return True
    if d[0][2] == d[1][1] == d[2][0] != '-':
        win = d[0][2]
        return True
    return False

def display():
    for row in d:
        print(" ".join(row))

def check():
    l = set(d[0] + d[1] + d[2])
    if "-" not in l:
        return True

def computer_move():
    for i in range(3):
        if d[i].count("O") == 2 and d[i].count("-") == 1:
            return (i, d[i].index("-"))
        if d[i].count("X") == 2 and d[i].count("-") == 1:
            return (i, d[i].index("-"))
    
    for i in range(3):
        col = [d[0][i], d[1][i], d[2][i]]
        if col.count("O") == 2 and col.count("-") == 1:
            return (col.index("-"), i)
        if col.count("X") == 2 and col.count("-") == 1:
            return (col.index("-"), i)
    
    diag1 = [d[0][0], d[1][1], d[2][2]]
    diag2 = [d[0][2], d[1][1], d[2][0]]
    
    if diag1.count("O") == 2 and diag1.count("-") == 1:
        return (diag1.index("-"), diag1.index("-"))
    if diag1.count("X") == 2 and diag1.count("-") == 1:
        return (diag1.index("-"), diag1.index("-"))
    if diag2.count("O") == 2 and diag2.count("-") == 1:
        return (diag2.index("-"), 2 - diag2.index("-"))
    if diag2.count("X") == 2 and diag2.count("-") == 1:
        return (diag2.index("-"), 2 - diag2.index("-"))

    if d[1][1] == "-":
        return (1, 1)

    for (i, j) in [(0, 0), (0, 2), (2, 0), (2, 2)]:
        if d[i][j] == "-":
            return (i, j)

    for i in range(3):
        for j in range(3):
            if d[i][j] == "-":
                return (i, j)

turn = random.choice(["X", "O"])
print(f"{turn} goes first!")

while flag:
    if turn == "X":
        x = tuple(map(int, input("Enter row and column of X input: ").strip().split()))
        if d[x[0]][x[1]] != '-':
            print("Spot already occupied, pick a new location.")
            continue

        d[x[0]][x[1]] = "X"

        if checkd() or any(checkr(i) for i in range(3)) or any(checkc(i) for i in range(3)):
            print(f"{win} Wins!")
            display()
            break

        display()
        if check():
            print("Tie")
            break

        turn = "O"  

    elif turn == "O":
        print("Computer is thinking...")
        y = computer_move()
        d[y[0]][y[1]] = "O"

        if checkd() or any(checkr(i) for i in range(3)) or any(checkc(i) for i in range(3)):
            print(f"{win} Wins!")
            display()
            break

        display()
        if check():
            print("Tie")
            break

        turn = "X"
