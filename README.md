# CypressUnplash
This is a basic project setup for testing web applications using the [Cypress](https://www.cypress.io/) framework. The project demonstrates end-to-end testing capabilities, including structure, configuration, and example tests.

## Table of Contents 

- [Features](#features )
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Project Structure](#project-structure)
- [Usage](#usage)
- [Writing Tests](#writing-tests)
- [Resources](#resources)

---
## Features

- End-to-end testing for web applications
- Cypress pre-configured for immediate use
- Example tests to get started
- Support for custom commands and reusable components

---

## Prerequisites

- [Node.js](https://nodejs.org/) (version >= 14.x)
- npm or [yarn](https://yarnpkg.com/)

---

## Installation

1. Clone the repository:
```bash
   git clone https://github.com/mni-linh/CypressUnplash
```
2. Navigate to the project directory:
```bash
   cd CypressUnplash
```
3. Install dependencies:
```bash
   npm install
```

## Project Structure
```md

CypressUnplash
├── cypress
│   ├── e2e
│   │   ├── common
│   │   │   └── common.js
│   │   ├── download
│   │   │   ├── download.feature
│   │   │   └── download.js
│   │   ├── follow
│   │   │   ├── follow.feature
│   │   │   └── follow.js
│   │   ├── list
│   │   │   ├── list.feature
│   │   │   └── list.js
│   │   ├── remove
│   │   │   ├── remove.feature
│   │   │   └── remove.js
│   │   └── update
│   │       ├── update.feature
│   │       └── update.js
│   ├── page-objects
│   │   ├── locators
│   │   │   ├── edit-profile.js
│   │   │   ├── home.js
│   │   │   ├── login.js
│   │   │   ├── menu-bar.js
│   │   │   ├── modal.js
│   │   │   └── profile.js
│   │   └── pages
│   │       ├── edit-profile.js
│   │       ├── home.js
│   │       ├── login.js
│   │       └── profile.js
│   ├── support
│   │   ├── commands.js
│   │   └── e2e.js
│   └── utils
│       ├── api
│       │   ├── endpoints
│       │   │   ├── collection.js
│       │   │   ├── photo.js
│       │   │   └── user.js
│       │   └── services
│       │       ├── collection.js
│       │       ├── photo.js
│       │       └── user.js
│       └── helpers
│           ├── common.js
│           └── request.js
├── .cypress-cucumber-preprocessorrc.json
├── .gitattributes
├── .prettierignore
├── .prettierrc
├── cypress.config.js
├── package-lock.json
├── package.json
└── README.md
```

### e2e

   Chứa các bài kiểm thử end-to-end, được phân chia thành các thư mục nhỏ hơn theo tính năng (download, follow, list, remove, update) hoặc module:

- .feature file: Định nghĩa các kịch bản kiểm thử theo cú pháp Gherkin (nếu sử dụng Cucumber Preprocessor).
- .js file: Chứa các bước kiểm thử (step definitions) tương ứng với các kịch bản trong file .feature.
- common: Chứa các hàm hoặc logic dùng chung cho nhiều bài kiểm thử, giúp tái sử dụng mã và giảm trùng lặp.

### page-object
   Mô hình hóa các trang web và thành phần trên trang theo mô hình Page Object Model (POM) để tổ chức mã kiểm thử dễ đọc và tái sử dụng:

- locators: Chứa định nghĩa locators (CSS selectors, XPath, v.v.) để tìm kiếm các phần tử trên giao diện. Tách biệt locators giúp dễ bảo trì nếu giao diện thay đổi.
- pages: Chứa các lớp (hoặc module) đại diện cho từng trang web. Các lớp này sử dụng locators và cung cấp các phương thức để tương tác với trang, ví dụ: login, navigateToProfile, editProfile.

### support
   Chứa các file thiết lập và lệnh hỗ trợ bổ sung cho các bài kiểm thử:

- commands: Định nghĩa các custom commands của Cypress (ví dụ: cy.login(), cy.uploadFile()).
- e2e.js: File thiết lập cho tất cả bài kiểm thử E2E, dùng để cấu hình global hooks (beforeEach, afterEach) hoặc import các lệnh từ commands.js.

### utils
   Chứa các tiện ích và API helper:

- api/endpoints: Định nghĩa các endpoint API của ứng dụng.
- api/services: Chứa các hàm gọi API sử dụng các endpoint đã định nghĩa, cung cấp giao diện để thao tác với API (ví dụ: getPhotos, createCollection)
- helpers: Chứa các hàm tiện ích dùng chung như xử lý HTTP (request.js) hoặc logic chung (common.js).

### Root Files
- .cypress-cucumber-preprocessorrc.json: Cấu hình cho Cucumber Preprocessor, bao gồm đường dẫn hoặc cài đặt parser cho file .feature.
- .gitattributes: Quản lý cách Git xử lý file, đặc biệt với các định dạng nhị phân.
- .prettierignore: Loại trừ các file khỏi Prettier.
- .prettierrc: Cấu hình Prettier.
- cypress.config.js: File cấu hình chính của Cypress, định nghĩa baseUrl, môi trường kiểm thử, và các thiết lập khác.
- package-lock.json: Chứa thông tin về các gói cần thiết cho dự án, bao gồm Cypress, Preprocessor, và các thư viện khác.
- package.json: Định nghĩa các dependencies và scripts cho dự án.
- README.md: Tài liệu hướng dẫn sử dụng và cấu trúc dự án.

## Usage

### Open Cypress Test Runner
   To open the Cypress test runner and run tests interactively:

```bash
   npx cypress open
```

### Run Tests in Headless Mode
   To execute tests in headless mode (useful for CI pipelines):

```bash
   npx cypress run
```

## Writing Tests

## Resources
- [Cypress Documentation](https://docs.cypress.io/app/get-started/why-cypress)
- [Cypress GitHub Repository](https://github.com/cypress-io/cypress)