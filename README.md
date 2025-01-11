# CypressUnplash
Cypress framework
#Documents
https://docs.cypress.io/guides/overview/why-cypress
npx cypress open

|_ cypress
   |_ e2e: chứa các bài kthử end-to-end, được phân chia các thư mục nhỏ hơn theo tính năng (download, follow, list, remove, update) hoặc module
+ .feature file: Định nghĩa các kịch bản kiểm thử theo cú pháp Gherkin (nếu sử dụng Cucumber Preprocessor).
+ .js file: Chứa các bước kiểm thử (step definitions) tương ứng với các kịch bản trong file .feature.
+ common: Chứa các hàm hoặc logic dùng chung cho nhiều bài kiểm thử, giúp tái sử dụng mã và giảm trùng lặp.
      |_ common
         |_ common.js
      |_ download
         |_ download.feature
         |_ download.js
      |_ follow
         |_ follow.feature
         |_ follow.js
      |_ list
         |_ list.feature
         |_ list.js
      |_ remove
         |_ remove.feature
         |_ remove.js
      |_ update
         |_ update.feature
         |_ update.js
   |_ page-objects: Mô hình hóa các trang web và thành phần trên trang, tuân theo mô hình Page Object Model (POM) để tổ chức mã kiểm thử một cách dễ đọc và tái sử dụng.
+ locators: Chứa các định nghĩa về locators (CSS selectors, XPath, v.v.) để tìm kiếm các phần tử trên giao diện. Tách biệt locators giúp dễ bảo trì nếu giao diện thay đổi.
+ pages: Chứa các lớp (hoặc module) đại diện cho từng trang web, sử dụng các locators để thao tác với các phần tử trên trang. Cung cấp các phương thức để tương tác với trang, như login, navigateToProfile, editProfile
      |_ locators
         |_ edit-profile.js
         |_ home.js
         |_ login.js
         |_ menu-bar.js
         |_ modal.js
         |_ profile.js
      |_ pages
         |_ edit-profile.js
         |_ home.js
         |_ login.js
         |_ profile.js
   |_ support: Chứa các file thiết lập và lệnh hỗ trợ bổ sung cho các bài kiểm thử.
+ command: Định nghĩa các custom commands của Cypress (ví dụ: cy.login(), cy.uploadFile()), giúp tái sử dụng logic phức tạp trong các bài kiểm thử.
+ e2e: File thiết lập cho tất cả bài kiểm thử E2E, thường được sử dụng để cấu hình global hooks (như beforeEach, afterEach) hoặc import các lệnh từ commands.js.
      |_ commands.js
      |_ e2e.js
   |_ utils: chứa các tiện ích và API helper
+ api: 
++ endpoints: Định nghĩa các endpoint API của ứng dụng.
++ services: Chứa các hàm gọi API sử dụng các endpoint đã định nghĩa, cung cấp giao diện để thao tác với API (ví dụ: getPhotos, createCollection)
      |_ api
         |_ endpoints
            |_ collection.js
            |_ photo.js
            |_ user.js
         |_ services
            |_ collection.js
            |_ photo.js
            |_ user.js
      |_ helpers: Chứa các hàm tiện ích dùng chung, như xử lý yêu cầu HTTP (request.js) hoặc logic chung (common.js).
         |_ common.js
         |_ request.js
|_ .cypress-cucumber-preprocessorrc.json: Cấu hình cho Cucumber Preprocessor, thường bao gồm đường dẫn hoặc cài đặt parser cho các file .feature
|_ .gitattibutes: Quản lý cách Git xử lý file (đặc biệt là với các định dạng nhị phân).
|_ .prettierignore: Cấu hình và loại trừ các file khỏi Prettier (công cụ định dạng mã).
|_ .prettierrc: nt
|_ cypress.config.js: File cấu hình chính của Cypress, định nghĩa baseUrl, môi trường chạy kiểm thử, và các thiết lập khác.
|_ package-lock.json: Chứa thông tin về các gói (packages) cần thiết cho dự án, bao gồm Cypress, Preprocessor, và các thư viện khác.
|_ package.json: nt
|_ README.md


<!-- //// -->
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
