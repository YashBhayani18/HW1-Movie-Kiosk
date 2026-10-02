# Movie Theater Ticket Kiosk

The **Movie Theater Ticket Kiosk** allows customers to browse available movies and showtimes, select an available seat, and purchase a ticket. The system verifies seat availability before completing the purchase and prevents the same seat from being sold more than once.

## Purpose

This repository is designed to practice and demonstrate software engineering tools and techniques, including:

- GitHub
- GitHub Issues
- GitHub Projects
- UML modeling
- diagrams.net
- Use case modeling
- Software requirements documentation

## Expanded Use Case: Purchase Ticket

### Primary Actor

**Customer**

### Precondition

The customer has selected:

- An available movie
- A valid showtime
- An available seat

### Main Flow

1. The customer selects a movie.
2. The customer selects a showtime for the movie.
3. The kiosk displays the available seats for the selected showtime.
4. The customer selects an available seat.
5. The kiosk verifies that the selected seat is still available.
6. The customer provides payment information.
7. The payment service processes and validates the payment.
8. The system creates the ticket.
9. The system marks the selected seat as unavailable for the selected showtime.
10. The kiosk displays a purchase confirmation to the customer.

### Postcondition

If the purchase is successful:

- The ticket is created and associated with the customer, movie, showtime, and seat.
- The selected seat is no longer available for that showtime.
- The payment is successfully processed.
- The customer receives a purchase confirmation.

### Alternative Flow: Seat No Longer Available

If the selected seat becomes unavailable before the purchase is completed:

1. The kiosk detects that the seat is no longer available.
2. The system prevents the purchase from proceeding with that seat.
3. The kiosk informs the customer that the seat is no longer available.
4. The customer is prompted to select another available seat.

### Alternative Flow: Payment Failure

If the payment service rejects or fails to process the payment:

1. The system does not complete the ticket purchase.
2. The selected seat remains available.
3. The kiosk informs the customer that the payment was unsuccessful.
4. The customer may retry the payment or select another payment method.

## System Requirements

The system should:

- Display available movies.
- Display showtimes for each movie.
- Display available seats for a selected showtime.
- Allow customers to select an available seat.
- Verify seat availability before completing the purchase.
- Process customer payments through a payment service.
- Create a ticket after successful payment.
- Mark the purchased seat as unavailable.
- Prevent duplicate seat purchases.
- Provide purchase confirmation to the customer.
- Handle unavailable seats and failed payments appropriately.

## Key Business Rule

> **A seat can be sold only once for a specific movie showtime.**

The system must verify seat availability at the time of purchase, not only when the customer initially selects the seat. This prevents two customers from purchasing the same seat concurrently.

## UML Modeling

The system can be modeled using UML diagrams such as:

- **Use Case Diagram** - Shows the interactions between the customer and the kiosk system.
- **Activity Diagram** - Shows the workflow for purchasing a ticket.
- **Sequence Diagram** - Shows interactions between the customer, kiosk, payment service, and ticketing system.
- **Class Diagram** - Represents major system entities such as Movie, ShowTime, Seat, Ticket, Customer, Payment, and PaymentService.
