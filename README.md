# APISpace 介绍
**本 API 服务由 [APISpace（apispace.com）](https://www.apispace.com/?utm_source=github&utm_term=shenfenzheng) 提供。**

APISpace 是 Eolink 旗下专业的 API 开放与交易平台，为广大企业以及个人开发者提供多维度、全方位的API接口，覆盖短信验证、天气查询、快递物流、OCR文字识别等海量 API 服务，帮助用户快速获取数据，降低获取数据的成本和难度，提升开发效率。

APISpace 提供15种开发语言的代码示例，分别是：
- Java(OK HTTP)
- HTTP
- cURL
- 微信小程序
- PHP(pecl_http)、PHP(cURL)
- Python(http.client)、Python(Requests)
- JavaScript(Jquery AJAX)、JavaScript(XHR)
- NodeJS(Native)、NodeJS(Request)
- Ruby(Net:Http)
- Shell(Httpie)、Shell(cUrl)

# 身份证识别OCR
传入身份证照片，识别照片文字信息并返回，包括姓名、身份证号码、性别、民族、出生年月日、地址、签发机关及有效期。

**使用该产品前，您需要通过 [https://www.apispace.com/eolink/api/ocr-idcard/introduction](https://www.apispace.com/eolink/api/ocr-idcard/introduction?utm_source=github&utm_term=shenfenzheng) 申请API服务**

本文档末尾提供了 Python(Requests) 的调用代码示例，可以前往文档末尾查看。

更多代码示例：[https://www.apispace.com/eolink/api/ocr-idcard/guidence/](https://www.apispace.com/eolink/api/ocr-idcard/guidence//?utm_source=github&utm_term=shenfenzheng)

### 应用场景

1.  #### 远程身份认证

使用身份证识别和人脸识别技术，自动识别录入用户身份信息，可应用于金融、保险、电商、O2O、直播等场景，对用户、商家、主播等进行实名身份认证，有效降低用户输入成本，控制业务风险

### 返回示例

```
{
    "words_result": {
        "name": "方xx",
        "gender": "男",
        "race": "汉",
        "birthday": "2006-10-2",
        "location": "上海市西藏南路瞿溪路弘辉名苑",
        "ID": ":371002200610020000"
    },
    "world_count": 6,
    "log_id": "1658994936041225280579"
}
      
```

### 服务保障
![image](https://user-images.githubusercontent.com/36323798/223980942-17e4f105-f01b-446e-b0df-d92bc942ec5c.png)

### Python(Requests) 调用代码示例

```
import requests

url = "https://eolink.o.apispace.com/ocr-idcard/id-ocr-cl"

payload = {"image":"","url":"http://data.eolinker.com/course/jPGsjfI069a149af72b64527bf14d3e11679a6eeaf2bd96","side":"0"}

headers = {
    "X-APISpace-Token":"",
    "Authorization-Type":"apikey",
    "Content-Type":"application/json"
}

response=requests.request("POST", url, data=json.dumps(payload), headers=headers)

print(response.text)

```
