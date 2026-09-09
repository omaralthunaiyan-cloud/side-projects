# Retail Business Database Design & ERD Documentation

A relational database design exercise for a small retail business, completed as a training assignment during my co-op at Devoteam.

## Overview

The document designs a normalized (3NF) relational database foundation for a retail business, covering customers, product categories, products, and sales, and documents the reasoning behind each design decision.

## Entities

- **CUSTOMER** — customer_id (PK), first_name, last_name, email (unique), phone
- **CATEGORY** — category_id (PK), name
- **PRODUCT** — product_id (PK), category_id (FK), name, price, stock_quantity
- **SALE** — sale_id (PK), customer_id (FK), sale_date, total_amount
- **SALE_ITEM** (junction table) — sale_item_id (PK), sale_id (FK), product_id (FK), quantity, unit_price_at_sale

## Relationship Logic

- **Category → Product** (1:N): one category contains many products, each product belongs to one category
- **Customer → Sale** (1:N): a customer can place multiple orders, supporting purchase-history tracking
- **Sale → Sale_Item** (1:N): each sale is composed of one or more line items, supporting multi-product transactions
- **Product → Sale_Item** (1:N): a product can appear across many sales transactions

## Engineering Highlights

- **Third Normal Form (3NF) compliance** — categories and sale details are separated into distinct entities to eliminate redundancy
- **Many-to-many resolution** — the `SALE_ITEM` junction table resolves the natural many-to-many relationship between products and sales
- **Historical data integrity** — a dedicated `unit_price_at_sale` field preserves the price at the moment of purchase, keeping financial reporting accurate even if a product's master price later changes

## Files

- `Engineering_Assignment.pdf` — full documentation, including the ERD diagram (Crow's Foot notation)
