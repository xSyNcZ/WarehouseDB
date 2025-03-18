# Warehouse Management Database

## Overview
This database system was designed to manage warehouse operations, including inventory tracking, employee management, and logistics. The database was created using Oracle SQL Developer and modeled with Oracle SQL Data Modeler.

## Database Structure
The database consists of the following main components:

### Physical Infrastructure
- **Hale (Halls)**: Physical buildings or large areas where goods are stored
- **Regaly (Shelves)**: Storage units organized in rows and columns within halls
- **Miejsca na palety (Pallet Spots)**: Specific locations on shelves where pallets can be placed

### Inventory Management
- **Palety (Pallets)**: Platforms used for storing and moving goods
- **Towary (Goods)**: Individual items stored in the warehouse
- **Kategorie towaru (Product Categories)**: Classification of goods with handling instructions

### Human Resources
- **Dzialy (Departments)**: Organizational units within the warehouse
- **Pracownicy (Employees)**: Staff working in the warehouse
- **Rodzaje pracownikow (Employee Types)**: Categories of employees with different permissions

### Equipment
- **Wozki widlowe (Forklifts)**: Heavy machinery for moving pallets
- **Wozki paletowe (Pallet Jacks)**: Manual equipment for moving pallets
- **Access Tables**: Tables tracking which employees can use which equipment

## Entity Relationships

The database employs several important relationships:
- Halls contain shelves and departments
- Shelves contain pallet spots
- Pallet spots hold pallets
- Pallets store goods
- Employees belong to departments and have specific employee types
- Employee types determine access to equipment

## Schema Details

### Main Tables
1. **hale**: Stores information about warehouse halls
2. **regaly**: Manages shelves within the halls
3. **"Miejsca na palety"**: Tracks specific pallet locations
4. **palety**: Contains information about pallets
5. **towary**: Stores product information
6. **"Kategorie towaru"**: Defines product categories
7. **dzialy**: Manages departments
8. **pracownicy**: Tracks employee information
9. **"Rodzaje pracownikow"**: Defines employee types
10. **"Wozki widlowe"**: Manages forklift information
11. **"Wozki paletowe"**: Tracks pallet jack information

### Junction Tables
1. **wp_rp**: Links employee types to pallet jacks
2. **ww_rp**: Links employee types to forklifts

## Setup Instructions

1. **Database Creation**:
   - Run the first section of the script to drop any existing tables and sequences
   - Run the second section to create all tables and relationships
   - Run the third section to populate the database with initial data

2. **Sequence Information**:
   - `seq_towary`: Auto-incrementing sequence for goods IDs
   - `seq_pracownicy`: Auto-incrementing sequence for employee IDs

## Data Model

The database was designed using Oracle SQL Data Modeler, with the following structure:
- 13 tables
- 2 indexes
- 25 constraints (primary keys, foreign keys)
- 2 sequences

## Sample Data

The script includes sample data for:
- 5 warehouse halls
- 7 departments
- 6 product categories
- 42 shelves distributed across 4 halls

## Notes

- The database uses sequences for auto-incrementing IDs
- Special care is taken with hazardous products (marked with `CZY_OSTROZNIE` flag)
- Equipment access is controlled through employee types
- The database includes tracking for equipment maintenance (e.g., forklift inspection dates)

## Contact

For questions or support regarding this database, please contact the database administrator.
