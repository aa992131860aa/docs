# RESTful API 常见问题解答（FAQ）


<a name="1"></a>1. **RESTful 如何设置离线消息保留时间？**

答： "opts" 设置 "qos" 值为 1 或 2，才能成功发送离线消息；设置 "time_to_live" 参数指定离线消息的保留时间，默认是5天，详见： [云巴的离线消息](product_kb_offline_message.md) 和 [RESTful API 的示例](restful_api_api_manual.md#HTTPPOST)。

---
<a name="2"></a>2. **加 opts 参数之后，可以用 get 请求吗？**

答： GET 方法不支持复杂参数，只是用来做简单测试；可以用 POST 方法，具体参考 [官方文档](restful_api_api_manual.md#HTTPPOST)。同时注意请求头的设置： Content-type: application/json。

---
<a name="3"></a>3. **RESTful API 可以指定 Message ID 吗？**

答： 云巴服务端随机生成 Message ID。

---
<a name="4"></a>4. **RESTful的`publish_to_alias_batch()`API 中别名 Alias 的最大数量有限制吗？**

答： 别名的数量建议在 1000 以下。

---
<a name="5"></a>5. **RESTful 的 Message 支持最大传送数据多大？**

答： 建议不要超过 1k。

---
<a name="6"></a>6. **使用 RESTful API 发送消息时需要区分 Android 和 iOS 平台设备吗？**

答： 不需要。 

**注**：apn_json 参数只针对 iOS 平台的 APNs 消息。具体参考 [官方文档](restful_api_api_manual.md#HTTPPOST)，apn_json 参数的完整设置方法可参考 [iOS 官方文档](https://developer.apple.com/library/ios/documentation/NetworkingInternet/Conceptual/RemoteNotificationsPG/Chapters/TheNotificationPayload.html#//apple_ref/doc/uid/TP40008194-CH107-SW1)。