import random

def vacuum_cleaner():
    rooms = [random.choice([0, 1]), random.choice([0, 1])]
    
    print("Initial status of rooms:")
    for i, status in enumerate(rooms):
        print(f"Room {i + 1}: {'Clean' if status == 1 else 'Dirty'}")

    while not all(room == 1 for room in rooms):
        for i in range(len(rooms)):
            if rooms[i] == 0:
                print(f"Room {i + 1} is dirty. Cleaning...")
                rooms[i] = 1
                print(f"Room {i + 1} is now clean.")
            else:
                print(f"Room {i + 1} is already clean.")
            
            rooms[i] = random.choice([0, 1])
        
        print("Status Update")
        for i, status in enumerate(rooms):
            print(f"Room {i + 1}: {'Clean' if status == 1 else 'Dirty'}")
    
    print("All rooms are clean")

if __name__ == "__main__":
    vacuum_cleaner()
