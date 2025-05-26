# Hotel-Room-Booking-System
# This project is done by Divyansh Rana (500121856)
class Hotel:
    def __init__(self, name, total_rooms):
        self.name = name
        self.total_rooms = total_rooms
        self.available_rooms = total_rooms

    def check_available_rooms(self):
        print(f"{self.name} has {self.available_rooms} rooms available out of {self.total_rooms}.")

    def book_room(self):
        if self.available_rooms > 0:
            self.available_rooms -= 1 
            print("Room Booked Successfully!")
        else:
            print("Sorry, no rooms available.")

def main():
    hotel_name = input("Enter The Hotel Name: ")
    while True:
        try:
            total_rooms = int(input("Enter The Total Number of Rooms: "))
            if total_rooms <= 0:
                raise ValueError("Number of rooms must be a positive integer.")
            break
        except ValueError as ve:
            print(ve)

    hotel = Hotel(hotel_name, total_rooms)

    while True:
        print("\n1. Check Available Rooms")
        print("2. Book a Room")
        print("3. Exit")

        choice = input("Enter your choice (1/2/3): ")

        if choice == '1':
            hotel.check_available_rooms()
        elif choice == '2':
            hotel.book_room()
        elif choice == '3':
            print("Thank you for using our hotel management system.")
            break
        else:
            print("Invalid choice. Please enter 1, 2, or 3.")

if __name__ == "__main__":
    main()
