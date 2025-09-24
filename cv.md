# Mikita Snitko

## Contacts

- **Phone**: +48 571-007-746
- **Location**: Poland, Bialystok
- **Email**: snitkonikita@gmail.com
- **Telegram**: @snitkon
- **GitHub**: Snitkon
- **Discord**: Mikita (@snitkon)

## About me

I am a Front-end Developer working with JavaScript, TypeScript, and React.js to build modern and user-friendly web applications. I also study and practice Node.js and Express to gain more full-stack development skills. I improve my technical and programming knowledge almost every day.

I graduated with a Bachelor’s degree from Kyiv National University of Economics and a Master’s degree in International Finance and Investment from Belarus State Economic University. Before IT, I worked in finance and the stock market.

In my free time, I enjoy reading business literature, doing sports, and learning new things.

## Skills

- **Programming Languages**:

  - JavaScript
  - TypeScript
  - HTML
  - CSS

- **Frameworks and Libraries**:

  - React
  - Redux
  - Next
  - Style-Components
  - SASS
  - TailwindCSS

- **Backend and Databases**:

  - Express
  - Node.js
  - MongoDB
  - Swagger

- **Tools**:

  - Git/GitHub
  - Webpack
  - Vite
  - Postman
  - Figma

## Code Example

```
class APIFeatures {
  constructor(query, queryString) {
    this.query = query;
    this.queryString = queryString;
  }

    // 1) Filtering

  filter() {
    const objQuery = Object.assign({}, this.queryString);
    const excludedFields = ['page', 'limit', 'sort', 'fields'];
    excludedFields.forEach((el) => delete objQuery[el]);

    let queryString = JSON.stringify(objQuery);
    queryString = queryString.replace(
      /\b(gte|gt|lte|lt)\b/g,
      (match) => `$${match}`
    );
    this.query = this.query.find(JSON.parse(queryString));

    return this;
  }

    // 2) Sorting

  sort() {
    if (this.queryString.sort) {
      const sortBy = this.queryString.sort.split(',').join(' ');
      this.query = this.query.sort(sortBy);
    } else {
      this.query = this.query.sort('createdAt');
    }
    return this;
  }

    // 3)Limiting Field

  limit() {

    if (this.queryString.fields) {
      const limitField = this.queryString.fields.split(',').join(' ');
      this.query = this.query.select(limitField);
    } else {
      this.query = this.query.select('-__v');
    }

    return this;
  }

    //? 4)Pagination

  pagination() {
    const page = this.queryString.page * 1 || 1;
    const limit = this.queryString.limit * 1 || 100;
    const skip = (page - 1) * limit;

    this.query = this.query.skip(skip).limit(limit);

    return this;
  }
}

module.exports = APIFeatures;
```

## Experience

- [My CV](https://snitkon.github.io/rsschool-cv/cv)

## Education

- **University**:

  - Kyiv National University of Economics
  - Belarus State Economic University

- **Сourses**:

  - The Rolling Scopes School (JavaScript/Front-End Stage#0)
    [Certificate (Stage #0).pdf](https://github.com/Snitkon/rsschool-cv/files/10228812/Certificate.Stage.0.pdf)
  - The Rolling Scopes School (JavaScript/Front-End Stage#1 - Stage#2)
    [Certificate (Stage #1 - Stage #2).pdf](https://github.com/Snitkon/rsschool-cv/files/10228823/Certificate.Stage.1.-.Stage.2.pdf)

## Languages

- **Russian**: Native speaker
- **English**: B1
