# 📈 OrderFlow
### A Stock Exchange Order Matching Engine built in C++17
==> A simplified but realistic stock exchange matching engine inspired by
how exchanges like NSE and NASDAQ process buy and sell orders.

==> The project focuses on clean Object-Oriented Design, extensibility,
and real-world software architecture rather than simply matching orders.

#  Features:
(1) Limit Orders
(2) Market Orders
(3) Price-Time Priority Matching
(4) Partial Order Fill
(5) Complete Order Fill
(6) Trade History
(7) Modular Design
(8)  Easy to Extend

#  System Architecture:
    Trader
   │
   ▼
Create Order
   │
   ▼
Order Book
   │
   ▼
Matching Engine
   │
   ├── Match Found ───► Execute Trade ───► Trade History
   │
   └── No Match ──────► Order Stays in Order Book               


# Matching Algorithm:

The engine continuously compares Best Buy Price with Best Sell Price Trade occurs only when Buy [Price >= Sell] Price Otherwise, orders remain inside the order book.

#  Price-Time Priority:

Suppose
BUY Book
₹252  (10:00)
₹252  (10:02)
₹250
A SELL order at ₹252 will match
First
10:00 Order
then
10:02 Order
This is exactly how real exchanges work.

==> OOP Concepts Used:

(1) Abstraction:
Order is an abstract base class.
The engine only works with
Order* without caring whether it's MarketOrder or LimitOrder.

(2) Inheritance:

From Order to it inherits in MarketOrder and LimitOrder

(3) Runtime Polymorphism:

The matching engine treats every order as
Order* Each derived class provides its own implementation.

(4) Encapsulation:

Every class owns and protects its own data.

(a) Trader manages trader information.

(b) Stock manages stock information.

(c) OrderBook manages all active orders.

(d) MatchingEngine performs only matching.

(5) Composition :

An order can not exists without its stock and Trade we can say that it shows composition in this project.


# Technologies : C++17,OOPS,STL 
#  Build:
```bash
mkdir build
cd build
cmake ..
make
./OrderFlow

#  Sample Execution :

text
 BEFORE MATCHING
BUY
252
250
248
SELL
245
247
249

 MATCHING :

Trade Executed
Buyer : Amit
Seller : Kishan
Price : 245
Quantity : 30
Trade Executed
Buyer : Amit
Seller : Rahul
Price : 247
Quantity : 50

# Learning Outcomes:
This project demonstrates:
- Real-world OOP

- Software Architecture

- Low Level Design

- Trading Engine Design

- Clean Code Principles

- Extensible System Design
