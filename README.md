# Spring微服務架構實戰

這是一個針對想深入掌握 Spring 生態系統的 Java 後端工程師量身打造的實戰課程專案。專案涵蓋從基礎的 Spring Framework、Spring Boot，到進階的 Spring Cloud 微服務架構，幫助你全面提升開發技能。

專案以線上咖啡館實戰項目貫穿全程，做到即學即用，不僅教授實戰技巧，更深入解析背後的關鍵機制。你將學會如何熟練使用 Spring 開發 Web 服務，理解 Spring Boot 核心實現原理，並利用 Spring Cloud 快速構建穩定且可擴展的微服務系統。

## 專案介紹

本專案重點示範如何在 Spring 微服務架構中配置多個資料源（DataSource），這是實務中常見且重要的需求。透過本專案，你將學會：

- 分離並管理多個資料源的配置，避免混淆與錯誤。
- 掌握 Spring Boot 自動配置與手動控制多資料源的兩種主要方式。
- 在程式中明確指定操作哪個資料源，確保資料操作正確。

## 先決條件

請確保你的開發環境已安裝以下軟體與工具：

- Java JDK 17
- Spring Boot 3.4.5
- Maven
- 其他必要的工具或相依套件

## 專案結構

- `src/main/java`：主要程式碼，包括多資料源配置與微服務邏輯。
- `src/main/resources`：配置檔案，包含多資料源的獨立設定。
- `application.yml` 或 `application.properties`：多資料源的URL、使用者名稱、密碼等配置。
- 重要元件：
  - 多資料源配置類別

## 快速開始

1. 克隆此倉庫：
   ```
   git clone https://github.com/SpringMicroservicesCourse/multi-datasource-demo
   ```
2. 進入專案目錄：
   ```
   cd multi-datasource-demo
   ```
3. 使用 Maven 編譯並啟動專案：
   ```
   mvn clean install
   mvn spring-boot:run
   ```
4. 確認服務啟動並連接多資料源成功。

## 進階說明

- 多資料源配置分為兩種方式：
  1. **完全手動控制配置**：排除 Spring Boot 自動配置，手動定義多個 DataSource 與 TransactionManager，適合複雜需求。
  2. **結合 Spring Boot 自動配置與 @Primary 標記**：指定主資料源，簡化設定。

- 在程式中使用 `@Primary`、`@Qualifier` 等註解明確指定資料源，避免資料錯用。

- 配置檔中請分開管理每個資料源的 URL、帳號、密碼等資訊，保持清晰。

- 測試階段建議透過日誌輸出確認資料源切換是否正確。

- 如需連接外部服務，請在 `application.yml` 中設定相關環境變數。

## 參考資源

- [Spring Boot 官方網站](https://spring.io/projects/spring-boot)
- [start.spring.io](https://start.spring.io/)
- [Spring Boot Actuator](https://docs.spring.io/spring-boot/docs/current/reference/html/actuator.html)