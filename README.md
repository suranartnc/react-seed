# React Seed
A development environment for starting up a react project with built-in API server.

## API Server

```bash
$ npm run api
```

### Examples

Get content of the menu with ID:1 including its category

```
GET http://localhost:4000/menus/1?_expand=category
```

Here is the result

```json
{
  id: 1,
  categoryId: 1,
  name: "Chinese Cabbage",
  images: "chinese_cabbage.jpg",
  price: 40,
  category: {
    id: 1,
    name: "Vegetable",
    images: "vegetable.svg"
  }
}
```

Get content of the category with ID:2 including all menus in it 

```
GET http://localhost:4000/categories/2?_embed=menus
```

Here is the result


```json
{
  id: 2,
  name: "Fresh foods",
  images: "freshfood.svg",
  menus: [
    {
      id: 4,
      categoryId: 2,
      name: "Fresh Chicken",
      images: "fresh_chicken.jpg",
      price: 60
    },
    {
      id: 5,
      categoryId: 2,
      name: "Sliced Pork",
      images: "sliced_pork.jpg",
      price: 60
    },
    {
      id: 6,
      categoryId: 2,
      name: "Fresh Egg",
      images: "fresh_egg.jpg",
      price: 10
    }
  ]
}
```