# Dominos Pizza Ordering System 🍕

A comprehensive pizza ordering system simulation built with Python and SQLite. Order pizzas, manage your cart, and experience a complete food ordering workflow with user authentication!

## 🎯 Features

### 🔐 User Management
- **Signup System** - Create account with email and username
- **Login Options** - Login with email or username
- **Secure Authentication** - Password confirmation and validation
- **User Database** - SQLite database for persistent user data

### 🍕 Menu System
- **7 Pizza Varieties** - From Margherita to Supreme
- **3 Size Options** - Regular, Medium, Large
- **4 Beverages** - Coca Cola, Sprite, Fanta, Root Beer
- **Dynamic Pricing** - Different prices for different sizes

### 🛒 Shopping Cart
- **Add Items** - Pizzas and drinks to cart
- **Smart Quantity Management** - Auto-updates quantity for same items
- **Edit Cart** - Remove items or adjust quantities
- **View Cart** - See all items with prices
- **Generate Bill** - Complete order summary

### 💰 Pricing Features
- Pizza prices range from ₹99 to ₹699
- Beverage prices range from ₹30 to ₹90.9
- Size-based pricing for pizzas
- Real-time total calculation

<div align="center">

### Don't want to clone? No problem! Run it instantly:

[![Open in Codespaces](https://img.shields.io/badge/Open%20in-Codespaces-green?style=for-the-badge&logo=github)](https://codespaces.new/sridharchinthaparthi/dominos-ordering-system)

**Perfect for:**
- 📱 Mobile browsing - Test from your phone!
- ⚡ Quick exploration - No setup required
- 🧪 Experimentation - Fork and modify

</div>

## 📋 Prerequisites

- Python 3.10 installed on your system
- SQLite3 (comes built-in with Python)

## 🔧 Installation

1. Clone the repository:
```bash
git clone https://github.com/sridahrchinthaparthi/dominos-ordering-system.git
```

2. Navigate to the project directory:
```bash
cd dominos-ordering-system
```

3. Run the application:
```bash
python dominos.py
```

**Note:** The SQLite database (`Dominos.db`) will be created automatically on first run.

## 🎮 How to Use

### First Time User

1. **Signup** (Option 1)
   - Enter email address
   - Create username
   - Set password with confirmation
   
2. **Login** (Option 2)
   - Choose email or username login
   - Enter credentials

### Ordering Process

3. **Order** (Option 4)
   - Select Pizza or Coke
   - Choose item from menu
   - Select size (for pizzas)
   - Enter quantity
   
4. **View Cart** (Option 5)
   - See all ordered items
   - Check quantities and prices
   
5. **Edit Cart** (Option 7)
   - Remove items
   - Adjust quantities
   
6. **Display Bill** (Option 6)
   - View final order summary
   - See total amount

## 📸 Example Usage

```
-----------Welcome to Dominos---------

Enter 1: signup
Enter 2: Login
Enter 3: Logout
Enter your choice: 1

Enter your email: john@example.com
Enter your username: john123
Enter your password: ****
Confirm your password: ****
Signup Successful

-----------Welcome to Dominos---------
Enter 4: Order
Enter your choice: 4

Enter 1: order Pizza's
Enter 2: order Cokes
Enter your choice: 1

         Item                   Regular    Medium    Large    
1 -- Margherita Pizza      -- 99 Rs.    199 Rs.    399 Rs.
2 -- Pepperoni Pizza       -- 169 Rs.   309 Rs.    499 Rs.
...

Enter your choice: 2
Enter 1: Regular
Enter 2: Medium
Enter 3: Large
Enter your choice: 2
Enter Pizza Quantity: 2
Item Added to your cart...
```

## 🍕 Menu Overview

### Pizza Menu

| ID | Pizza Name | Regular | Medium | Large |
|----|------------|---------|--------|-------|
| 1 | Margherita Pizza | ₹99 | ₹199 | ₹399 |
| 2 | Pepperoni Pizza | ₹169 | ₹309 | ₹499 |
| 3 | Vegetarian Pizza | ₹119 | ₹299 | ₹399 |
| 4 | Hawaiian Pizza | ₹349 | ₹425 | ₹498 |
| 5 | BBQ Chicken Pizza | ₹390 | ₹449 | ₹529 |
| 6 | Meat Lovers Pizza | ₹199 | ₹299 | ₹499 |
| 7 | Supreme Pizza | ₹229 | ₹499 | ₹699 |

### Beverage Menu

| ID | Drink Name | Price |
|----|------------|-------|
| 8 | Coca Cola | ₹90 |
| 9 | Sprite | ₹50 |
| 10 | Fanta | ₹30 |
| 11 | Root Beer | ₹90.9 |

## 💻 Code Structure

```python
import sqlite3
import copy

class Dominos:
    # Class attributes
    menu = [...]      # Pizza menu
    coke = [...]      # Beverage menu
    
    def __init__(self):
        self.cart = []
        self.signed = False
        self.log = False
    
    # Core methods
    def signup()        # User registration
    def login()         # User authentication
    def logout()        # End session
    def order()         # Order items
    def order_pizza()   # Pizza ordering
    def order_coke()    # Beverage ordering
    def open_cart()     # View cart
    def edit_cart()     # Modify cart
    def disp_bill()     # Display final bill
```

## 🗃️ Database Schema

```sql
CREATE TABLE USER(
    UN VARCHAR(10),      -- Username
    PWD VARCHAR(18),     -- Password
    EMAIL VARCHAR(30)    -- Email address
)
```

## 🔒 Security Features

- ✅ Password confirmation during signup
- ✅ Email and username uniqueness validation
- ✅ Login required for ordering
- ✅ Session management with logout
- ✅ Persistent user data in SQLite

## 🎯 Key Functionalities

### Cart Management
- **Smart Merging** - Same items with same size auto-merge
- **Quantity Tracking** - Real-time quantity updates
- **Price Calculation** - Automatic total calculation
- **Category Tracking** - Separate regular, medium, large items

### Order Flow
1. User must login to order
2. Select pizza or beverage
3. Choose size (for pizzas)
4. Specify quantity
5. Add to cart
6. Option to add more items
7. View/edit cart anytime
8. Generate final bill

## 🛠️ Future Enhancements

- [ ] Add delivery address management
- [ ] Implement payment gateway integration
- [ ] Add order history tracking
- [ ] Include discount/coupon system
- [ ] Add order tracking status
- [ ] Implement admin panel for menu management
- [ ] Add ratings and reviews
- [ ] Include favorite orders feature
- [ ] Add order time estimation
- [ ] Implement email notifications
- [ ] Create mobile app version
- [ ] Add multiple payment options
- [ ] Include loyalty points system
- [ ] Add customization options (extra cheese, toppings)
- [ ] Implement scheduled ordering

## 🧪 Testing Guide

### Test Scenario 1: User Registration
1. Signup with valid email and username
2. Try duplicate email → Should fail
3. Try duplicate username → Should fail
4. Test password mismatch → Should retry

### Test Scenario 2: Ordering
1. Order pizza (Medium Pepperoni, Qty: 2)
2. Order same pizza again → Should merge quantities
3. Order different size → Should be separate item
4. Add beverages to cart

### Test Scenario 3: Cart Operations
1. View cart with multiple items
2. Remove partial quantity
3. Remove complete item
4. Try removing more than available → Should fail

## ⚠️ Important Notes

- This is a **simulation** for educational purposes
- No actual payment processing
- Database is local (Dominos.db file)
- Session data resets on app restart
- For production use, implement proper security measures

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/sridahrchinthaparthi/dominos-ordering-system/issues).

### Ways to Contribute:
- Add more menu items
- Implement GUI interface
- Add payment integration
- Improve security features
- Add order history
- Create admin dashboard

### Steps to Contribute:
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📧 Contact

**Sridhar Chinthaparthi**
- Email: sridharchinthaparthi@gmail.com
- GitHub: [@sridahrchinthaparthi](https://github.com/sridahrchinthaparthi)

## 📜 License

This project is open source and available under the [MIT License](LICENSE).

## ⭐ Show your support

Give a ⭐️ if you enjoyed this project!

---


**🍕 Enjoy Your Virtual Pizza! 🎉**
