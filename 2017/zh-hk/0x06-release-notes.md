# RN 發行說明

## 由2013到2017有乜轉變？

過去四年轉變快咗好多，所以OWASP Top 10都要改變。我地重構咗成個OWASP Top 10，成個方法翻新咗，用咗一個新嘅數據召集程序，同社群一齊合作，重新將風險排序，將每一個風險都由頭寫過晒，仲加咗而家常用嘅框架同語言既參考。

過去幾年，應用程式嘅基礎科技同架構都變得幾顯著：

* 以node.js撰寫嘅微服務(Microservices)同埋Spring Boot都取代緊傳統單一架構既應用程式。微服務有佢地自己既保安難題，包括建立微服務，軟件容器「箱」(譯按： Docker嘅container即係一個「貨櫃箱」)，秘密管理，等等之間既信任。以往唔預計會係互聯網直接掂到既舊程式而家就放喺應用程式接口或者RESTful網站服務，由單頁應用程式（SPAs)同手機應用程式（Mobile Applications)去使用。編程架構上既假設，例如只有信任既使用者(caller)，以經唔再啱啦。
* 以JavaScript框架例如Angular同React所撰寫嘅單頁應用程式，容許非常模組化，多功能既網站前端（Front-end)出現。傳統上以伺服器端提供嘅服務，而家喺客戶端提供，產生咗新嘅保安挑戰。
* JavaScript成為咗以node.js運行伺服器端，同埋係客戶端運行嘅現代網站框架例如Bootstrap, Electron, Angular, 同React嘅主要語言。

## 由數據支撐嘅新問題

* **A4:2017-XML External Entities (XXE)** 係一個主要由源始碼分析保安測試工具(source code analysis security testing tools) ([SAST](https://www.owasp.org/index.php/Source_Code_Analysis_Tools)) 嘅數據所支撐嘅新嘅類別.

## 由社群支撐嘅新問題

我哋請求社群為兩個前瞻嘅弱點類別提供獨具慧眼嘅意見。喺收到超過五百個意見同移除一啲已經有數據支撐嘅問題之後（例如敏感資料洩漏同XXE），兩個新嘅問題係：

* **A8:2017-唔安全既deserialization**，喺受影響嘅平台容許遠端執行程式碼（remote code execution）或者操控敏感嘅物件(sensitive object manipulation）
* **A10:2017-唔足夠嘅記錄同監測**, 對惡意活動同突破防線嘅偵測，事故應變，同埋數碼鑑證做成阻礙或顯著咁延遲

## 合併或者退役，不過唔會唔記得

* **A4-對物件有唔安全嘅直接引用(Insecure Direct Object References)** 同 **A7-欠缺功能層面嘅存取控制(Missing Function Level Access Control)** 合併成為 **A5:2017-壞咗嘅存取控制**.
* **A8-偽做跨網站請求(Cross-Site Request Forgery (CSRF))**, 由於好多框架都包含咗[CSRF 防衛措施](https://www.owasp.org/index.php/Cross-Site_Request_Forgery_(CSRF)), 呢個風險只係5%嘅應用程式搵到。
* **A10-未經驗證嘅引導同轉發(Unvalidated Redirects and Forwards)**, 只係喺8%嘅應用程式搵到，被XXE風險排擠出十大。

![0x06-release-notes-1](images/0x06-release-notes-1.png)
