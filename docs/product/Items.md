# 📝 Product Item Documentation  


## Product Items  

### Product Item Entity  

The following properties are defined for the `product_items` table:  

| Name                | Type      | Description                                                  | Unique | Required |  
|---------------------|-----------|--------------------------------------------------------------|--------|----------|  
| id                  | INT       | Primary key, unique template ID                              | ✅     | ✅      |  
| product_name        | String    | Name of the product item                                     | ❌     | ✅      |  
| product_description | String    | Description of the product item                              | ❌     | ❌      |  
| product_image       | String    | Image of the product item                                    | ❌     | ❌      |
| product_price       | Decimal   | Price of the product item (Default: 0) -> Wallet Type        | ❌     | ✅      |
| sort_order          | INT       | Sort order of the product item (Default: 0)                  | ❌     | ✅      |  
| is_active           | Boolean   | Indicates if the product item is active (Default: true)      | ❌     | ✅      |  
| is_highlight        | Boolean   | Indicates if the product item is highlighted (Default: true) | ❌     | ✅      |  
| is_public           | Boolean   | Indicates if the product item is public (Default: true)      | ❌     | ✅      |  
| code                | String    | Shareable code, can be regenerated                           | ❌     | ❌      |  
| start               | DateTime  | The start date of the product item                           | ❌     | ❌      |  
| end                 | DateTime  | The end date of the product item                             | ❌     | ❌      |  
| user_id             | INT       | Foreign key from User table, indicating the creator          | ❌     | ✅      |  
| created_at          | DateTime  | Timestamp when the record was created                        | ❌     | ✅      |  
| updated_at          | DateTime  | Timestamp when the record was last updated                   | ❌     | ✅      |  


### Product Item Membership Entity  

The following properties are defined for the `product_item_member` table:  

| Name                   | Type      | Description                                                  | Unique | Required |  
|------------------------|-----------|--------------------------------------------------------------|--------|----------|  
| id                     | INT       | Primary key, unique submission ID                            | ✅     | ✅      |  
| product_item_id        | INT       | Foreign key from product item table                          | ❌     | ✅      |  
| idt_member_id          | INT       | Foreign key from Member table (Invitee)                      | ❌     | ✅      | 
| idt_member_referral_id | INT       | Foreign key from User table (Invitor) from Member Referral   | ❌     | ❌      |
| user_id                | INT       | Foreign key from User table, who create this record          | ❌     | ✅      | 
| created_at             | DateTime  | Timestamp when the record was created                        | ❌     | ✅      |  
| updated_at             | DateTime  | Timestamp when the record was last updated                   | ❌     | ✅      |  

#### Invited Member:
- Invited Membership: Each member will have `idt_member_id` after invited by Invitor.
- Product Item Member: Each item will linked to the `idt_member_id` (Invitee) and `idt_member_referral_id` (Invitor).

#### Notification:
- Member will received a notification trough WhatsApp/Email with pre-filled link to the Product Item detail/status.
- Pre-filled link will direct Invited Member (Invitee) to the Product Item detail/status using their data (without login).


## Notes  

- **Unique**: Ensures the uniqueness of the values entered into a property of a database table.  
- **Required**: Ensures that the values entered into a property of a database table cannot be NULL.  
