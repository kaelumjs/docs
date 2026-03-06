---
title: CLI Reference
description: Kaelum command line interface for scaffolding projects.
sidebar:
  order: 2
---

## Usage

```bash
npx kaelum create [project-name] [--template <web|api>]
```

### Interactive Mode

```bash
npx kaelum create
```

Prompts for project name and template selection.

### Direct Mode

```bash
# Web template
npx kaelum create my-app --template web

# API template
npx kaelum create my-api --template api
```

## Templates

### Web Template

MVC structure for page-driven sites:

```
my-web-app/
├── public/
│   └── style.css
├── views/
│   └── index.html
├── controllers/
│   └── pagesController.js
├── middlewares/
│   └── logger.js
├── routes.js
├── app.js
└── package.json
```

### API Template

Optimized for REST API projects:

```
my-api/
├── controllers/
│   └── usersController.js
├── middlewares/
│   └── authMock.js
├── routes.js
├── app.js
└── package.json
```

## After Scaffolding

```bash
cd my-app
npm install
npm start
```

:::note
Requires Node.js 18+ and npm 8+.
:::
