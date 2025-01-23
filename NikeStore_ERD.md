# Nike Shoe Store Entity-Relationship Diagram

```mermaid
erDiagram
PRODUCT {
  integer productID PK
  string name
  string color
  string size
  float price
}
CUSTOMER {
  integer customerID PK
  string firstname
  string lastname
  integer age
  integer phone
}
SALE {
  integer productID FK
  integer amount FK
  integer customerID FK
  integer saleID FK, PK
}
INVENTORY {
  integer saleID PK, FK
  integer productID PK
  integer stockLevel PK
}

PRODUCT ||--o{ SALE : includes
PRODUCT ||--o{ INVENTORY : manages
CUSTOMER ||--o{ SALE : makes
```

## ERD Description
**PRODUCT** - Tracks Nike shoe models, their categories, and prices

**CUSTOMER** - Tracks customer IDs, their names, their age group, and their phone number

**SALE** - Tracks Nike shoe model sales, the amount, which customer made a purchase, and a sale identifier for the inventory
  
**INVENTORY** - Tracks the sale identifier for profit, tracks the item(s) sold, and tracks the stock level
  

### Relationships
1. **PRODUCT to INVENTORY**: Products can be stored in many different inventory locations
2. **CUSTOMER to SALE**: A customer can make purchases
3. **PRODUCT to SALE**: A sale can include multiple different products
