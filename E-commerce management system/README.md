# E-commerce Management System - Communication Diagram

## Overview

This repository contains the **Communication Diagram** for an e-commerce management system. The system showcases how various components interact with each other to facilitate the complete workflow of online shopping, from browsing products to order delivery. The diagram focuses on the flow of messages between the customer, website, backend systems, delivery system, and payment gateway.

## Communication Diagram Breakdown

### Participants:
1. **Alice: Customer**  
   The primary user of the system who browses and makes purchases.
   
2. **Amazon: Website**  
   The central platform that mediates between the customer, backend, delivery, and payment systems.
   
3. **Backend**  
   The server that handles internal operations like product fetching, adding products to the cart, and cart size management.
   
4. **Ecart: Delivery System**  
   A third-party delivery system that handles the registration and confirmation of orders.
   
5. **Gpay: Payment Gateway**  
   The gateway system used by the customer for making payments.

---

### Communication Flow:

1. **Browse (`browse()`):**  
   Alice starts by browsing the available products on the Amazon Website.

2. **Add to Cart (`addToCart(id, n)`):**  
   Alice adds products to the cart by specifying the product ID and the quantity.

3. **Checkout (`checkOut()`):**  
   Alice initiates the checkout process, which generates an order ID.

4. **Submit Order (`submitOrder()`):**  
   If the cart is not empty, Alice submits the order.

5. **Fetch Products (`fetchProducts()`):**  
   The Amazon website fetches the product details from the Backend.

6. **Load Products (`loadProducts()`):**  
   The Backend loads the products into the cart.

7. **Register Order (`Register(orderID)`):**  
   Upon successful submission, the Amazon website registers the order with the Ecart delivery system.

8. **Delivery Confirmation (`deliveryConfirmation()`):**  
   The Ecart system provides a delivery confirmation date for the order.

9. **Invoice Generation (`invoice(orderID)`):**  
   If the order is confirmed, Alice receives an invoice with the order ID and date.

10. **Order Rejection (`rejectmsg()`):**  
   If the order is rejected (e.g., out-of-stock products), a rejection message is sent back to Alice.

11. **Backend Cart Add (`addToCart(id, n)`):**  
   The Backend is updated with the product and quantity added to Alice’s cart.

12. **Cart Size (`cartSize(cid)`):**  
   The Backend checks the size of the cart using Alice's cart ID.

13. **Make Payment (`makePayment(upiNo, orderID)`):**  
   Alice proceeds to payment, and the payment request is sent to the Gpay payment gateway.

14. **Payment Confirmation (`confirmation()`):**  
   Gpay sends a confirmation message back to the Amazon Website, indicating whether the payment was successful.
