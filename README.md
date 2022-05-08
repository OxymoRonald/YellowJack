# YellowJack
YellowJack Point Of Sale (POS)

## Products
Products are stored in a JSON string in the file: assets/itemlist.json

There are two type of items, items and groups.
1. Items
Items are set up in the following manner:  
- Group name (Item Group)
  - Group type (items)
Followed by a list of items in the group that are set up as followes
  - Item name (Item 1)
    - Item description
    - Item image (that is placed in the "products" directory)
    - Price  

```JSON
"Item Group":{
  "type": "items",
  "Item 1":{
      "description": "Description 1",
      "image": "image1.png",
      "price": 80
  },
  "Item 2":{
      "description": "description 2",
      "image": "image2.png",
      "price": 100
  }
}
```

2. Combos
Combos are set up in the following manner:  
- Group name (Combo Group)
  - Group type (combos)
Followed by a list of items in the group that are set up as followes
  - Combo name (Combo 1)
    - Combo description
    - Combo image (that is placed in the "products" directory)
    - Items list 
      - Item name:amount (The name of items in the list **must** match existing items)
    - Price 
```JSON
"Combo Group":{
  "type": "combos",
  "Combo 1":{
      "description": "Combo 1 description",
      "image": "combo1.png",
      "items":{
          "Item 1":2, 
          "Item 2":4
      },
      "price":230
  },
  "Combo 2":{
      "description": "Combo 2 description",
      "image": "combo2.png",
      "items":{
          "Item 1":5, 
          "Item 2":2
      },
      "price":430
  }
}
```

## Product Images
Product images are stored in the directory: products/*.png

Images should be square and 90x90 pixels for optimal performance. Other sizes will work but might thow off the styling.

## Page generation
The page is automatically generated from the data stored in the JSON file. If the JSON is invalid the page will most likely not load.
