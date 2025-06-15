---
tags: [identity-management, user-profile, database-schema, personal-information, data-verification]
---
# 🪪 Memberships

## Membership Entity
The following properties for idt_members table:

| Name                      | Type      | Description                                | Unique | Required  |
|---------------------------|-----------|--------------------------------------------|--------|-----------|
| idt_member_id             | INT       | Primary key, unique member ID              |   ✅   |    ✅    |
| idt_member_name           | String    | Name of the member                         |   ❌   |    ✅    |
| idt_member_description    | String    | Description of the member                  |   ❌   |    ❌    |
| idt_member_icon           | String    | Icon of the member                         |   ❌   |    ❌    |
| idt_member_type_id        | INT       | Foreign key from member Type table         |   ❌   |    ✅    |
| idt_member_referral_id    | INT       | Foreign key from Member table (Invitor)    |   ❌   |    ✅    |
| user_id                   | INT       | Foreign key from User table                |   ❌   |    ❌    |


## Membership Type Entity
The following properties for idt_member_types table:

| Name                    | Type      | Description                                 | Unique | Required  |
|-------------------------|-----------|---------------------------------------------|--------|-----------|
| idt_member_type_id           | INT       | Primary key, unique membership ID                 |   ✅   |    ✅    |
| idt_member_type_code         | String(6) | Code of the membership type               |   ❌   |    ✅    |
| idt_member_type_name         | String    | Name of the membership type               |   ❌   |    ✅    |
| idt_member_type_description  | String    | Description of the member type               |   ❌   |    ❌    |
| idt_member_is_deleted   | boolean   | Is trx type deleted (Default: False)        |   ❌   |    ✅    |


NOTE
- Unique: Ensures the uniqueness of the values entered into a property of a database table.
- Required: Ensures that the values entered a property of a database table can NOT be NULL.
