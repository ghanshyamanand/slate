---
title: Full Text Search API

language_tabs:
  - json
  - ruby

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the TastyTab’s full text search  API! This API will help you to search food items available in database .

There are different case by which a user can search a food items in a particular restaurant .

A user can search a paticular food item in a restaurant or user also has facility to search all food items of particular food category .


# Authentication

To interact with TastyTab’s API you need to authenticate yourself by including provided access_token via query string parameter.

TastyTab uses access token to allow access to the API. You can register a new TastyTab access token by contacting us.

TastyTab expects for the access_token to be included in all API requests to the server in a header that looks like the following:

access_token: "8de9358df65b86b643a206cb795355a2"

# Search Food Items

## Search Particular Food Item

```ruby
require 'unirest'

response = Unirest.get "http://localhost:3000/api/v1/restaurants/2/search", headers:{ "Accept" => "application/json" }, parameters: {search_value: "FRIED ZUCCHINI" , access_token: "testing"}

```



> The above command returns JSON structured like this:

```ruby
[
    {
        "id": 12,
        "name": "FRIED ZUCCHINI",
        "pos_name": "Fried Zucchini",
        "price": 6.95,
        "description": null,
        "is_out_of_stock": false,
        "item_modifiers": [],
        "food_images": [
            {
                "food_image": {
                    "id": 1,
                    "image": {
                        "image": {
                            "url": "/uploads/food_image/image/1/f1.jpg",
                            "thumb": {
                                "url": "/uploads/food_image/image/1/thumb_f1.jpg"
                            }
                        }
                    }
                }
            },
            {
                "food_image": {
                    "id": 2,
                    "image": {
                        "image": {
                            "url": "/uploads/food_image/image/2/f2.jpg",
                            "thumb": {
                                "url": "/uploads/food_image/image/2/thumb_f2.jpg"
                            }
                        }
                    }
                }
            },
            {
                "food_image": {
                    "id": 3,
                    "image": {
                        "image": {
                            "url": "/uploads/food_image/image/3/f3.jpg",
                            "thumb": {
                                "url": "/uploads/food_image/image/3/thumb_f3.jpg"
                            }
                        }
                    }
                }
            },
            {
                "food_image": {
                    "id": 4,
                    "image": {
                        "image": {
                            "url": "/uploads/food_image/image/4/f4.jpg",
                            "thumb": {
                                "url": "/uploads/food_image/image/4/thumb_f4.jpg"
                            }
                        }
                    }
                }
            },
            {
                "food_image": {
                    "id": 5,
                    "image": {
                        "image": {
                            "url": "/uploads/food_image/image/5/f5.jpg",
                            "thumb": {
                                "url": "/uploads/food_image/image/5/thumb_f5.jpg"
                            }
                        }
                    }
                }
            },
            {
                "food_image": {
                    "id": 6,
                    "image": {
                        "image": {
                            "url": "/uploads/food_image/image/6/f6.jpg",
                            "thumb": {
                                "url": "/uploads/food_image/image/6/thumb_f6.jpg"
                            }
                        }
                    }
                }
            }
        ]
    }
]

```

```json
[
    {
        "id": 12,
        "name": "FRIED ZUCCHINI",
        "pos_name": "Fried Zucchini",
        "price": 6.95,
        "description": null,
        "is_out_of_stock": false,
        "item_modifiers": [],
        "food_images": [
            {
                "food_image": {
                    "id": 1,
                    "image": {
                        "image": {
                            "url": "/uploads/food_image/image/1/f1.jpg",
                            "thumb": {
                                "url": "/uploads/food_image/image/1/thumb_f1.jpg"
                            }
                        }
                    }
                }
            },
            {
                "food_image": {
                    "id": 2,
                    "image": {
                        "image": {
                            "url": "/uploads/food_image/image/2/f2.jpg",
                            "thumb": {
                                "url": "/uploads/food_image/image/2/thumb_f2.jpg"
                            }
                        }
                    }
                }
            },
            {
                "food_image": {
                    "id": 3,
                    "image": {
                        "image": {
                            "url": "/uploads/food_image/image/3/f3.jpg",
                            "thumb": {
                                "url": "/uploads/food_image/image/3/thumb_f3.jpg"
                            }
                        }
                    }
                }
            },
            {
                "food_image": {
                    "id": 4,
                    "image": {
                        "image": {
                            "url": "/uploads/food_image/image/4/f4.jpg",
                            "thumb": {
                                "url": "/uploads/food_image/image/4/thumb_f4.jpg"
                            }
                        }
                    }
                }
            },
            {
                "food_image": {
                    "id": 5,
                    "image": {
                        "image": {
                            "url": "/uploads/food_image/image/5/f5.jpg",
                            "thumb": {
                                "url": "/uploads/food_image/image/5/thumb_f5.jpg"
                            }
                        }
                    }
                }
            },
            {
                "food_image": {
                    "id": 6,
                    "image": {
                        "image": {
                            "url": "/uploads/food_image/image/6/f6.jpg",
                            "thumb": {
                                "url": "/uploads/food_image/image/6/thumb_f6.jpg"
                            }
                        }
                    }
                }
            }
        ]
    }
]

```

This endpoint search particular food item in a particular restaurant.

### HTTP Request

`GET  http://tastytab.com/api/v1/restaurants/2/search?access_token=testing&search_value=FRIED ZUCCHINI`

### Query Parameters

Parameter | Description
--------- | -----------
search_value | Make sure it's does not empty and it should be valid food item name .


<aside class="success">
A particular food item and its complete details is fetched from database .
</aside>

## Get all food items of particular category

```ruby
require 'kittn'

response = Unirest.get "http://localhost:3000/api/v1/restaurants/2/search", headers:{ "Accept" => "application/json" }, parameters: {search_value: "pizza" , access_token: "testing"}
```


> The above command returns JSON structured like this:

```ruby
{
    "food_items": [
        {
            "food_item": {
                "id": 16,
                "name": "GREEK STYLE",
                "pos_name": "Greek Style",
                "price": 4.99,
                "description": null,
                "is_out_of_stock": false,
                "item_modifiers": [
                    {
                        "item_modifier": {
                            "id": 97,
                            "pos_name": "Whole Wheat",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 98,
                            "pos_name": "Thin ",
                            "price": null
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 99,
                            "pos_name": "Thick",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 100,
                            "pos_name": "Red",
                            "price": null
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 101,
                            "pos_name": "Mozzarella",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 102,
                            "pos_name": "Tomatoe",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 103,
                            "pos_name": "Eggplant",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 104,
                            "pos_name": "Garlic",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 105,
                            "pos_name": "Feta",
                            "price": 0.5
                        }
                    }
                ],
                "food_images": []
            }
        },
        {
            "food_item": {
                "id": 17,
                "name": "CREATE YOUR OWN",
                "pos_name": "Create Your Own",
                "price": 3.99,
                "description": "add toppings to create a pizza",
                "is_out_of_stock": false,
                "item_modifiers": [
                    {
                        "item_modifier": {
                            "id": 106,
                            "pos_name": "Whole Wheat",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 107,
                            "pos_name": "Thin ",
                            "price": null
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 108,
                            "pos_name": "Thick",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 109,
                            "pos_name": "Red",
                            "price": null
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 110,
                            "pos_name": "Alfredo Sauce",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 111,
                            "pos_name": "Spicy sauce",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 112,
                            "pos_name": "Pesto",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 113,
                            "pos_name": "Chipotle Sauce",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 114,
                            "pos_name": "No Sauce",
                            "price": null
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 115,
                            "pos_name": "White Sauce",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 116,
                            "pos_name": "BBQ",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 117,
                            "pos_name": "Mozzarella",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 118,
                            "pos_name": "Shrimp",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 119,
                            "pos_name": "Prosciutto",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 120,
                            "pos_name": "Broccoli",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 121,
                            "pos_name": "Onions Green",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 122,
                            "pos_name": "Anchovies",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 123,
                            "pos_name": "Green Olives",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 124,
                            "pos_name": "Green Pepper",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 125,
                            "pos_name": "Olives Black",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 126,
                            "pos_name": "Pesto",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 127,
                            "pos_name": "Garlic",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 128,
                            "pos_name": "Pineapple",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 129,
                            "pos_name": "Goat Cheese",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 130,
                            "pos_name": "Corn",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 131,
                            "pos_name": "Eggplant",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 132,
                            "pos_name": "Ham",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 133,
                            "pos_name": "Tomatoe",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 134,
                            "pos_name": "Pancheta",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 135,
                            "pos_name": "Sundried",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 136,
                            "pos_name": "Onion",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 137,
                            "pos_name": "Spinach",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 138,
                            "pos_name": "Bacon",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 139,
                            "pos_name": "Basil",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 140,
                            "pos_name": "Extra Cheese",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 141,
                            "pos_name": "Zucchini",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 142,
                            "pos_name": "Riccotta",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 143,
                            "pos_name": "Chorizo",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 144,
                            "pos_name": "Artichoke ",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 145,
                            "pos_name": "Onions Red",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 146,
                            "pos_name": "Sliced Tomatoes",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 147,
                            "pos_name": "Salami",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 148,
                            "pos_name": "Jalapeno",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 149,
                            "pos_name": "Feta",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 150,
                            "pos_name": "Mushroom",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 151,
                            "pos_name": "Cilantro",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 152,
                            "pos_name": "BBQ",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 153,
                            "pos_name": "Pepperoni",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 154,
                            "pos_name": "Chicken",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 155,
                            "pos_name": "Black Beans",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 156,
                            "pos_name": "Italian Sausage",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 157,
                            "pos_name": "Beef",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 158,
                            "pos_name": "Linguica",
                            "price": 0.5
                        }
                    }
                ],
                "food_images": []
            }
        },
        {
            "food_item": {
                "id": 18,
                "name": "BBQ CHIX",
                "pos_name": "BBQ Chix",
                "price": 4.99,
                "description": null,
                "is_out_of_stock": false,
                "item_modifiers": [
                    {
                        "item_modifier": {
                            "id": 159,
                            "pos_name": "Whole Wheat",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 160,
                            "pos_name": "Thin ",
                            "price": null
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 161,
                            "pos_name": "Thick",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 162,
                            "pos_name": "BBQ",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 163,
                            "pos_name": "Red",
                            "price": null
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 164,
                            "pos_name": "Mozzarella",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 165,
                            "pos_name": "Chicken",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 166,
                            "pos_name": "Onion",
                            "price": 0.5
                        }
                    }
                ],
                "food_images": []
            }
        },
        {
            "food_item": {
                "id": 19,
                "name": "ALL MEAT",
                "pos_name": "All Meat",
                "price": 4.99,
                "description": null,
                "is_out_of_stock": false,
                "item_modifiers": [
                    {
                        "item_modifier": {
                            "id": 167,
                            "pos_name": "Whole Wheat",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 168,
                            "pos_name": "Thin ",
                            "price": null
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 169,
                            "pos_name": "Thick",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 170,
                            "pos_name": "Red",
                            "price": null
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 171,
                            "pos_name": "Beef",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 172,
                            "pos_name": "Ham",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 173,
                            "pos_name": "Italian Sausage",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 174,
                            "pos_name": "Linguica",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 175,
                            "pos_name": "Pepperoni",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 176,
                            "pos_name": "Salami",
                            "price": 0.5
                        }
                    },
                    {
                        "item_modifier": {
                            "id": 177,
                            "pos_name": "Extra Cheese",
                            "price": 0.5
                        }
                    }
                ],
                "food_images": []
            }
        }
    ]
}
```

This endpoint retrieves all food items of particular category  .

<aside class="warning">If you're not using an administrator API key, note that some kittens will return 403 Forbidden if they are hidden for admins only.</aside>

### HTTP Request

`GET http://tastytab.com/api/v1/restaurants/2/search?access_token=testing&search_value=Pizza`

### URL Parameters

Parameter | Description
--------- | -----------
search_value | It should be valid food item name or valid category name
<aside class="success">
All food items and their details of particular category is fetched from database .
</aside>
