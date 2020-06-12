# Groceries table
Grocery ID: Table Key
Grocery Name: name of the grocery item
Grocery Quantity: Quantity that the grocery item is available in. May be volume, mass or number
Grocery Size: Some grocery items have different sizes, as well as quantity
Grocery Category: Differentiate types of groceries to help functions determine how to aggregate data

## Examples

    {
        "Grocery": {
            "Name": "Eggs",
            "Quantity": 12,
            "Size": "Medium"
        },
        "Grocery": {
            "Name": "Eggs",
            "Quantity": 12,
            "Size": "Large"
        },
        "Grocery": {
            "Name": "Carrots",
            "Quantity": 2,
            "Size": "KG"
        },
        "Grocery": {
            "Name": "Flour",
            "Quantity": 5,
            "Size": "KG"
        },
        "Grocery": {
            "Name": "Lettuce",
            "Quantity": 1,
            "Size": "Medium"
        },
        "Grocery": {
            "Name": "Butter",
            "Quantity": 454,
            "Size": "G"
        }
    }

## Challenges
* Naming conventions are required to ensure like items appear in sequence. Rice - Jasmine, Rice - Basmati, Rice - Arborio as {Name, Variety} vs Arborio Rice, Basmati Rice, Jasmine Rice which will sort poorly in lists.
* Differences in quantities/measurements make it difficult to handle aggregating items that are purchased by weight, volume, counts or package. NoSQL allows for a more flexible Attribute model, eliminating attributes that are not applicable.
* If RDBMS, splitting groceries into a few tables could help with grouping
    CREATE TABLE Groceries
    (
        Grocery_ID int,
        Grocery_Name nvarchar(100)
    );
    CREATE TABLE Grocery_Quantity
    (
        Grocery_ID int, -- ID Of parent Grocery Item
        Quantity decimal, -- What precision?
        Quantity_Measure nvarchar(20) -- measurement unit, Grams, ML, Count
    );
    CREATE TABLE Measures
    (
        Measure_ID int,
        Measure_Name nvarchar(100), -- Gram, KG, ML, Count, Size
    );
* Some items that should be measured in weight are measured in volume. Particularly problematic in recipes