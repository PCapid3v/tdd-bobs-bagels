# User story

## Part 1

```txt
As a member of the public
So I can order a bagel when I want to
I'd like to add an item to my basket
Nouns: public, bagel, item, basket
Verbs: Order, Add

As a member of the public,
So that I can change my order
I'd like to remove an item from my basket
Nouns: public, item, basket, order
Verbs: Change, Remove
```

## Part 2

```txt
As a member of the public,
So that I can not overfill my small bagel basket
I'd like to know when my basket is full when I try adding an item beyond my basket capacity.
Nouns: Public, small bagel basket, item, basket capacity
Verbs: overfill, try adding

As a Bob's Bagels manager,
So that I can record more sales
I’d like to create baskets with larger capacity when I need to.
Nouns: Manager, baskets
Verbs: record, create,

As a member of the public
So that I can maintain my sanity
I'd like to know if I try to remove an item that doesn't exist in my basket. 
Nouns: public, sanity, item, basket
Verbs: maintain, know, remove
```

## Part 3

```txt
As a member of the public,
So that I can know how much my bagels are,
I’d like to see the price of each item before I add it to my basket.
Nouns: public, bagels, price, item, basket
Verbs: know, see, add

As a member of the public
So that I can buy many of my favorite bagel
I'd like to be able to add the same type of bagel to my basket more than once
Nouns: public, favorite bagel, bagel, basket
Verbs: buy many, add multiple,

As a member of the public,
So that I can prepare to pay
When I go to checkout I'd like to know the total sum of the bagels in my basket
Nouns: public, checkout, sum of bagels,
Verbs: pay, know
```

| Methods       | Inputs | Data | Scenario | Outputs |
| ------------- | ------ | ---- | -------- | ------- |
| addToBasket(sku) | sku(@string)| | valid sku | add item to basket, message "item added" |
|||| invalid sku | return message "item not found" |
|||| no sku input | return message "item sku required" |
|||| basket is full | return message "basket full" |
|||| sku already in basket | increase quantity of item in basket, message "item added" |
|||||
| removeFromBasket(sku) | sku(@string)| | valid sku, sku in basket | remove item to basket, message "item removed" |
|||| valid sku, sku not in basket | return message "item not in cart" |
|||| invalid sku | return message "item not stocked" |
|||| no sku input | return message "item sku required" |
|||||
| checkBasketQuantity()|||basket is (@array)|return sum of each item quantity |
||||basket is not (@array)|return "misconfigured basket" |
|||||
| setBasketCapacity(capacity)|capacity(@Number)| @Number > 0| positive integer input | change capacity, return capacity |
|||| not positive number input | return "please enter positive number value" |
|||||
| findBasketItem(sku) | sku(@string) || valid sku, sku in basket | return item object |
|||| valid sku, sku not in basket | return "item not found" |
|||| invalid sku | return "item is not stocked" |
|||||
|displayItemPrice(sku)| sku(@string) | | valid sku | return item price | x |
|||| invalid sku | return "sku not found" |
|||| no sku input | return "sku required" |
|||||
|displayBasketSum()||| items in basket | return sum of items.price |
|||| no items in basket | return 0 |
|||||
| findInventoryItem(sku)| sku(@string)||valid sku, sku in inventory | return item object |
|||| valid sku, sku not in inventory | return "item not found" |
