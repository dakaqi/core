### 票据

票据是一次交易的载体及凭证。

票据基础信息包含：

| 参数名 | 必填 | 类型 | 示例值 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| code\_type | 是 | string\(16\) | CODE\_TYPE\_TEXT | Code展示类型，"CODE\_TYPE\_TEXT"，文本；"CODE\_TYPE\_BARCODE"，一维码 ；"CODE\_TYPE\_QRCODE"，二维码；"CODE\_TYPE\_ONLY\_QRCODE",二维码无code显示；"CODE\_TYPE\_ONLY\_BARCODE",一维码无code显示； |
| payment | 是 | jason | 见示例 | 价格信息。包含货币类型、价格、借贷种类 |
| price\_type | 是 | int | 1 | 货币的类型。1为限定性货币，也就是虚拟货币。2为非限定性货币，也就是人民币 |
| price | 是 | int | 100 | 价格 |
| accounting | 是 | int | 1 | 借或者贷。1为借，2为贷。 |
| title | 是 | string（27） | 巡逻员 | 票券名，字数上限为9个汉字。\(建议涵盖卡券属性、服务及金额\)。 |
| sub\_title | 否 | string（54） | 罗山路街道 | 副标题，字数上限为18个汉字。 |
| notice | 是 | string（48） | 现场需进行签到 | 票券使用提醒，字数上限为16个汉字。 |
| description | 是 | string（3072） | 任务的具体描述 | 票券使用说明，字数上限为1024个汉字。 |
| sku | 是 | Json结构 | 具体不同票全业务对应的信息 | 商品信息。包含quantity。 |
| quantity | 是 | int | 100000 | 票券库存的数量，不支持填写0，上限为100000000。 |
| date\_info | 是 | Json结构 |  | 使用日期，有效期的信息。包含begin\_timestamp和end\_timestamp |
| begin\_timestamp | 否 | unsigned int | 14300000 | 表示起用时间。从1970年1月1日00:00:00至起用时间的秒数，最终需转换为字符串形态传入。（东八区时间，单位为秒） |
| end\_timestamp | 否 | unsigned int | 15300000 | 表示结束时间，建议设置为截止日期的23:59:59过期。（东八区时间，单位为秒） |
| source | 否 | string（36） | 志愿汇 | 第三方来源名，例如志愿汇、打卡器。 |
| custom\_url\_name | 否 | string（15） | 立即报名 | 自定义跳转外链的入口名字。 |
| custom\_url | 否 | string（128） | "xxxx.com" | 自定义跳转的URL。 |
| custom\_url\_sub\_title | 否 | string（18） | 暂未接入，跳转可报名 | 显示在跳转链接的提示语。 |
| promotion\_url\_name | 否 | string（15） | 点击获取志愿保险 | 营销场景的自定义入口名称。 |
| promotion\_url | 否 | string（128） | XXXX.com | 入口跳转外链的地址链接。 |
| promotion\_url\_sub\_title | 否 | string（18） | 价值150万的志愿保险保障。 | 显示在营销入口的提示语。 |
| get\_limit | 否 | int | 1 | 每人可领券的数量限制。 |
| can\_share | 否 | bool | false | 票券领取页面是否可分享。 |
| can\_give\_friend | 否 | bool | false | 票券是否可转赠。 |

岗位类票

| 参数名 | 必填 | 类型 | 示例值 | 描述 |
| :--- | :--- | :--- | :--- | :--- |
| card\_type | 是 | string\(24\) | position | 岗位类门票 |
| base\_info | 是 | Json结构 | 见示例。 | 基本的票圈数据，见上表，所有卡券通用。 |
| meeting\_detail | 是 | string\(3072\) | 本次会议于2015年5月10号在广州举行，会场地点：xxxx。 | 会议详情。 |
| map\_url | 否 | string\(128\) | xxx.com | 会场导览图。 |



