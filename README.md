<h1 align="center">
  <img alt="GoStack" src="./assets/gostack.png">
</h1>

<p align="center">
  <img alt="Last commit on GitHub" src="https://img.shields.io/github/last-commit/tavareshenrique/gostack11-typeorm-relations?color=7D40E7">
  <img alt="Made by Rocketseat" src="https://img.shields.io/badge/made%20by-Rocketseat-%20?color=7D40E7">
  <img alt="Project top programing language" src="https://img.shields.io/github/languages/top/tavareshenrique/gostack11-typeorm-relations?color=7D40E7">
  <img alt="Repository size" src="https://img.shields.io/github/repo-size/tavareshenrique/gostack11-typeorm-relations?color=7D40E7">
  <img alt="GitHub license" src="https://img.shields.io/github/license/tavareshenrique/gostack11-typeorm-relations?color=7D40E7">
</p>

<p align="center">
  <a href="#information_source-content">ℹ️ Conteúdo</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#rocket-technologies">🚀 Tecnologias</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#computer-author">💻 Autor</a>&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;
  <a href="#memo-license">📝 Licença</a>
</p>

<p align="center">
  Desafio para criar uma nova aplicação para aprender novas coisas e treinar o que aprendi utilizando Node junto ao TypeScript, incluindo o uso de banco de dados com o TypeORM, e relacionamentos ManyToMany durante o Bootcamp GoStack 11 da Rocketseat.
</p>

---

# :information_source: Conteúdo

- [Customers](#customers)
  - [Create](#create-customers)
- [Products](#customers)
  - [Create](#create-products)
- [Orders](#customers)
  - [ListById](#list-order-by-id)
  - [Create](#create-orders)

---

# Customers

## **Create** Customers

Create a Customer.

* **URL**

  `/customers`

* **Method:**

  `POST`

* **URL Params**

   **Required:**

    None

    **Optional:**

* **Data Params**

  ```json
    {
     "name": "Henrique",
     "email": "ihenrits@gmail.com"
    }
    ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:**

    ```json
    {
      "name": "Henrique",
      "email": "ihenrits@gmail.com",
      "id": "975c68ed-23f9-43de-ac0b-01b868379b90",
      "created_at": "2020-05-31T00:04:41.633Z",
      "updated_at": "2020-05-31T00:04:41.633Z"
    }
    ```

---

# Products

## **Create** Products

Create a Products.

* **URL**

  `/products`

* **Method:**

  `POST`

* **URL Params**

   **Required:**

    None

    **Optional:**

* **Data Params**

  ```json
  {
   "name": "Product",
   "price": 10.20,
   "quantity": 10
  }
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:**

    ```json
    {
      "name": "Product",
      "price": 10.2,
      "quantity": 10,
      "id": "7065fcd4-7f3e-4ef5-a0da-2e2d67172c0b",
      "created_at": "2020-05-31T01:12:53.922Z",
      "updated_at": "2020-05-31T01:12:53.922Z"
    }
    ```

---

# Orders

## List **Order** By Id

List Order By Id.

* **URL**

  `/orders/:id`

* **Method:**

  `GET`

* **URL Params**

   **Required:**

    id - Order ID

    **Optional:**

* **Data Params**

  None

* **Success Response:**

  * **Code:** 200 <br />
    **Content:**

    ```json
    {
      "id": "aaafa544-26a4-42d0-9efd-382cfb8107bc",
      "created_at": "2020-05-31T03:53:29.511Z",
      "updated_at": "2020-05-31T03:53:29.511Z",
      "customer": {
        "id": "bfacf2b5-4148-4838-a762-c0a9ca00899e",
        "name": "Henrique",
        "email": "ihenrits@gmail.com",
        "created_at": "2020-05-31T03:50:59.849Z",
        "updated_at": "2020-05-31T03:50:59.849Z"
      },
      "order_products": [
        {
          "id": "7d8fa389-de71-46bb-b21b-9567f352d804",
          "product_id": "123797ec-326b-4aea-a42c-50eac705b286",
          "order_id": "aaafa544-26a4-42d0-9efd-382cfb8107bc",
          "price": "10.20",
          "quantity": 10,
          "created_at": "2020-05-31T03:53:29.511Z",
          "updated_at": "2020-05-31T03:53:29.511Z"
        }
      ]
    }
    ```

---

## **Create** Orders

Create a Order.

* **URL**

  `/orders`

* **Method:**

  `POST`

* **URL Params**

   **Required:**

    None

    **Optional:**

* **Data Params**

  ```json
  {
    "customer_id": "bfacf2b5-4148-4838-a762-c0a9ca00899e",
    "products": [
      {
        "name": "Product 2",
        "price": 10.20,
        "quantity": 10,
        "id": "123797ec-326b-4aea-a42c-50eac705b286"
      }
    ]
  }
  ```

* **Success Response:**

  * **Code:** 200 <br />
    **Content:**

    ```json
    {
      "customer": {
        "id": "bfacf2b5-4148-4838-a762-c0a9ca00899e",
        "name": "Henrique",
        "email": "ihenrits@gmail.com",
        "created_at": "2020-05-31T03:50:59.849Z",
        "updated_at": "2020-05-31T03:50:59.849Z"
      },
      "order_products": [
        {
          "product_id": "123797ec-326b-4aea-a42c-50eac705b286",
          "price": "10.20",
          "quantity": 10,
          "order_id": "aaafa544-26a4-42d0-9efd-382cfb8107bc",
          "id": "7d8fa389-de71-46bb-b21b-9567f352d804",
          "created_at": "2020-05-31T03:53:29.511Z",
          "updated_at": "2020-05-31T03:53:29.511Z"
        }
      ],
      "id": "aaafa544-26a4-42d0-9efd-382cfb8107bc",
      "created_at": "2020-05-31T03:53:29.511Z",
      "updated_at": "2020-05-31T03:53:29.511Z"
    }
    ```

---

# :rocket: Tecnologias

- [TypeScript](https://www.typescriptlang.org/)
- [ts-node-dev](https://github.com/whitecolor/ts-node-dev)
- [express](https://expressjs.com/pt-br/)
- [express-async-errors](https://github.com/davidbanham/express-async-errors#readme)
- [cors](https://github.com/expressjs/cors)
- [cross-env](https://github.com/kentcdodds/cross-env)
- [pg](https://date-fns.org/)
- [reflect-metadata](https://date-fns.org/)
- [tsyringe](https://date-fns.org/)
- [typeorm](https://date-fns.org/)
- [tsyringe](https://date-fns.org/)
- [eslint](https://eslint.org/)
- [prettier](https://prettier.io/)

---

# :computer: Autor

<table>
  <tr>
    <td align="center">
      <a href="http://github.com/tavareshenrique/">
        <img src="https://avatars1.githubusercontent.com/u/27022914?v=4" width="100px;" alt="Henrique Tavares"/>
        <br />
        <sub>
          <b>Henrique Tavares</b>
        </sub>
       </a>
       <br />
       <a href="https://www.linkedin.com/in/tavareshenrique/" title="Linkedin">@tavareshenrique</a>
       <br />
       <a href="https://github.com/tavareshenrique/gostack11-typeorm-relations/commits?author=tavareshenrique" title="Code">💻</a>
    </td>
    <td align="center">
      <a href="https://github.com/Rocketseat/">
        <img src="https://avatars0.githubusercontent.com/u/28929274?s=200&v=4" width="100px;" alt="Rocketseat"/>
        <br />
        <sub>
          <b>Rocketseat</b>
        </sub>
       </a>
       <br />
       <a href="https://www.linkedin.com/in/tavareshenrique/" title="Linkedin">@Rocketseat</a>
       <br />
       <a href="https://github.com/tavareshenriquegostack11-conceitos-nodejs/commits?author=tavareshenrique" title="Code">💻</a>
    </td>
  </tr>
</table>

---

# :memo: Licença

Este projeto está licenciado sob a licença MIT - consulte o arquivo [LICENSE.md](https://github.com/tavareshenrique/gostack11-typeorm-relations/blob/master/LICENSE.md) para obter detalhes.
