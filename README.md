# Ride-Sharing OOP Mini Project 🚗📱

A comprehensive Object-Oriented Programming (OOP) implementation of a ride-sharing system (like Uber/Ola) in Python. This project demonstrates core OOP principles including inheritance, encapsulation, and polymorphism through a functional simulation.

## 🚀 Features

- **User Management**: Base `User` class with registration and validation logic for Riders and Drivers.
- **Ride Booking**: Riders can request rides and join shared rides.
- **Driver Assignment**: Drivers have vehicle details, availability status, and location tracking.
- **Ride Pooling**: Smart `PoolManager` to match riders with existing rides based on route.
- **Fare Calculation**: Dynamic fare calculation based on distance.
- **Route Matching**: Logic to determine if a pickup/drop location is on an active route.

## 🛠️ System Architecture

### Core Classes

| Class | Description |
|-------|-------------|
| **User** | Base class handling common attributes (name, email, phone, password) and validation. |
| **Rider** | Inherits from `User`. Can request rides, join shared rides, and track ride history. |
| **Driver** | Inherits from `User`. Manages vehicle details, current location, and availability. |
| **Vehicle** | Stores vehicle information (number, model, type). |
| **Location** | Represents geographical coordinates (latitude, longitude). |

### Service Classes

| Class | Description |
|-------|-------------|
| **SharedRide** | Represents an active ride instance with driver, route, and passenger details. |
| **PoolManager** | Manages active rides and handles logic for matching usage requests to existing rides. |
| **RouteMatcher** | Utility to calculate distances and check if a location matches a ride's route. |
| **FareCalculator**| Calculates ride fares based on distance and other factors. |

## 💻 Usage Example

```python
# 1. Initialize System Components
matcher = RouteMatcher()
fare_calc = FareCalculator()
pool_manager = PoolManager()

# 2. Create Locations
pickup_loc = Location(12.9716, 77.5946)
drop_loc = Location(12.9352, 77.6245)

# 3. Register a Driver with a Vehicle
vehicle = Vehicle("KA-01-MJ-1234", "Tesla Model 3", "Sedan")
driver = Driver("Alice Smith", "alice@example.com", "9876543210", "securePass123", vehicle)
driver.update_location(pickup_loc)

# 4. Register a Rider
rider = Rider("Bob Jones", "bob@example.com", "9123456789", "password888")

# 5. Create/Request a Ride
ride = SharedRide("RIDE-001", driver, pickup_loc, drop_loc, seats=3)
pool_manager.create_ride(ride, rider)

# 6. Calculate Fare
total_fare = fare_calc.calculate_total_fare(ride)
print(f"Total Fare: {total_fare}")
```

## 📂 Project Structure

- `Ride_Sharing.ipynb`: The main Jupyter Notebook containing all class definitions and simulation logic.

## 👨💻 Author

**Kunal Biradar**

GitHub: [https://github.com/Kunal171205](https://github.com/Kunal171205)

## 📜 License

This project is for educational purposes to demonstrate OOP concepts.
