# E-commerce Back End Starter Code

<p align="center">
    <img src="https://img.shields.io/badge/Javascript-yellow" />
    <img src="https://img.shields.io/badge/express-orange" />
    <img src="https://img.shields.io/badge/Sequelize-blue"  />
    <img src="https://img.shields.io/badge/mySQL-blue"  />
    <img src="https://img.shields.io/badge/dotenv-green" />
</p>

## Description

Internet retail, also known as **e-commerce**, is the largest sector of the electronics industry, having generated an estimated US$29 trillion in 2017 (Source: United Nations Conference on Trade and Development). E-commerce platforms like Shopify and WooCommerce provide a suite of services to businesses of all sizes. Due to the prevalence of these platforms, developers should understand the fundamental architecture of e-commerce sites.

This week I will build the back end for an e-commerce site. I’ll take a working Express.js API and configure it to use Sequelize to interact with a MySQL database.

Because this application won’t be deployed, I’ll also create a walkthrough video that demonstrates its functionality and all of the following acceptance criteria being met.

## Table of Contents

- [Description](#Description)
- [User-Story](#User-Story)
- [Acceptance-Criteria](#Acceptance-Criteria)
- [Demo](#Demo)
- [Installation](#Installation)
- [Usage](#Usage)
- [Features](#Features)

## User Story

```md
AS A manager at an internet retail company
I WANT a back end for my e-commerce website that uses the latest technologies
SO THAT my company can compete with other e-commerce companies
```

## Acceptance Criteria

```md
GIVEN a functional Express.js API
WHEN I add my database name, MySQL username, and MySQL password to an environment variable file
THEN I am able to connect to a database using Sequelize
WHEN I enter schema and seed commands
THEN a development database is created and is seeded with test data
WHEN I enter the command to invoke the application
THEN my server is started and the Sequelize models are synced to the MySQL database
WHEN I open API GET routes in Insomnia for categories, products, or tags
THEN the data for each of these routes is displayed in a formatted JSON
WHEN I test API POST, PUT, and DELETE routes in Insomnia
THEN I am able to successfully create, update, and delete data in my database
```

## Demo

The following video shows an example of the application being used from the command line:

[![A video thumbnail shows the command-line employee management application with a play button overlaying the view.](./Assets/12-sql-homework-video-thumbnail.png)](https://2u-20.wistia.com/medias/2lnle7xnpk)

## Installation

`npm init`

`npm install mysql2`

`npm install sequelize`

`npm install dotenv`

## Usage

Run the following command at the root of your project and answer the prompted questions:

`mysql -u root -p`

Enter PW when promted

`source db/schema.sql`

`quit`

`npm run seed`

`npm start`

## Features

I’ll use the [MySQL2] (https://www.npmjs.com/package/mysql2) and [Sequelize] (https://www.npmjs.com/package/sequelize) packages to connect your Express.js API to a MySQL database and the [dotenv package] (https://www.npmjs.com/package/dotenv) to use environment variables to store sensitive data, like your MySQL username, password, and database name.

I'll use the schema.sql file in the db folder to create a database using MySQL shell commands. I'll use environment variables to store sensitive data, like your MySQL username, password, and database name.

**Database Models**:

Your database should contain the following four models, including the requirements listed for each model:

- `Category`

  - `id`

  - Integer

  - Doesn't allow null values

  - Set as primary key

  - Uses auto increment

  - `category_name`

  - String

  - Doesn't allow null values

- `Product`

  - `id`

  - Integer

  - Doesn't allow null values

  - Set as primary key

  - Uses auto increment

  - `product_name`

  - String

  - Doesn't allow null values

  - `price`

  - Decimal

  - Doesn't allow null values

  - Validates that the value is a decimal

  - `stock`

  - Integer

  - Doesn't allow null values

  - Set a default value of 10

  - Validates that the value is numeric

  - `category_id`

  - Integer

  - References the `category` model's `id`

- `Tag`

  - `id`

  - Integer

  - Doesn't allow null values

  - Set as primary key

  - Uses auto increment

  - `tag_name`

  - String

- `ProductTag`

  - `id`

  - Integer

  - Doesn't allow null values

  - Set as primary key

  - Uses auto increment

  - `product_id`

  - Integer

  - References the `product` model's `id`

  - `tag_id`

  - Integer

  - References the `tag` model's `id`

**Associations**:
You'll need to execute association methods on your Sequelize models to create the following relationships between them:

- `Product` belongs to `Category`, as a category can have multiple products but a product can only belong to one category.

- `Category` has many `Product` models.

- `Product` belongs to many `Tag` models. Using the `ProductTag` through model, allow products to have multiple tags and tags to have many products.

- `Tag` belongs to many `Product` models.

---

© 2022 xndroli. Confidential and Proprietary. All Rights Reserved.
