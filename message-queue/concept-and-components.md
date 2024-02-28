---
description: >-
  Message queue giải quyết các vấn đề liên quan đến tính bất đồng bộ và tương
  tác giữa các thành phần trong hệ thống phân tán là một phần quan trọng trong
  kiến trúc hệ thống microservices.
---

# Concept and Components

**Message queue** là một hộp thư, cho phép các thành phần/service trong một hệ thống (hoặc nhiều hệ thống), gửi thông tin cho nhau.

<figure><img src="../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

Một hệ thống sử dụng Message Queue thường có những thành phần sau đây:

* **Message**: Thông tin được gửi đi (có thể là text, binary hoặc JSON)
* **Message Queue**: Nơi chứa những message này, cho phép producer và consumer có thể trao đổi với nhau.
* **Producer**: Chương trình/service tạo ra thông tin, messgage đưa thông tin vào message queue.
* **Consumer**: Chương trình/service nhận message từ message queue và xử lý chúng.
* Một chương trình/service có thể **vừa là producer, vừa là consumer**&#x20;
* **Broker**: Trong một số trường hợp, có một thành phần trung gian (message broker) quản lý và duy trì hàng đợi. Broker có thể giúp quản lý tải, đảm bảo độ tin cậy và cung cấp các tính năng như publish-subscribe.

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

## Các loại message queue: <a href="#cac-loai-message-queue-2" id="cac-loai-message-queue-2"></a>

#### 1. Point-to-point <a href="#id-1-point-to-point-3" id="id-1-point-to-point-3"></a>

Point-to-point là khi chỉ có một hàng đợi và một consumer duy nhất dể xử lý các tin nhắn trong hàng đợi: VD: **RabbitMQ**

<figure><img src="../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

#### 2. Publisher-Subscriber <a href="#id-2-publisher-subscriber-4" id="id-2-publisher-subscriber-4"></a>

Publisher-Subscriber (publisher - nhà sản xuất) gửi tin nhắn đến hàng đợi (gọi là Topic) và tất cả subscriber (người đăng ký) vào cùng 1 Topic đều sẽ nhận được tin nhắn trong Topic đó. VD: **RabbitMQ, Apache Kafka**

<figure><img src="../.gitbook/assets/image (3).png" alt=""><figcaption></figcaption></figure>

