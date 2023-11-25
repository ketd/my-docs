## 规则01：全部小写，用破折号而不是缩写


| **URI**                    | **Status** | **Why**                                  |
| -------------------------- | ---------- | ---------------------------------------- |
| /customers                 | Good       | 复数和小写                               |
| /customers/16/phone-number | Good       | 小写字母和连字符用于分隔单词             |
| /customers/16/address/home | Good       | 小写字母，无斜杠，用正斜杠显示层次关系。 |
| /users/{userId}            | Good       | 变量使用驼峰命名法，变量名中不使用连字符 |
| /Customers                 | Bad        | 标题大小写                               |
| /generalMembers            | Bad        | 驼峰命名法，没有连字符来分隔单词         |
| /MenuItems/GeneralMembers  | Bad        | 帕斯卡命名法                             |
| /customers/16/tel-no       | Bad        | 缩写                                     |
|                            |            |                                          |
| /customers/16/phone_number | Bad        | 下划线                                   |
| /customers/16/phonenumber  | Bad        | 没有单词间的分隔                         |
| /users/{user-id}           | Bad        | 变量应该使用驼峰命名法，单词之间使用连字符 |





## 规则 02：使用正斜杠表示层级关系
在 API URI 中始终使用正斜杠来表示层级关系。为了理解这个规则，请考虑以下场景和 API 端点之间的关系。
商店可以有顾客，顾客可以下许多订单，每个订单可以有送货地址、菜单项和账单。
