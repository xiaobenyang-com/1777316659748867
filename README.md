# 生物年龄计算服务 Biomarker Ranges

基于Morgan Levine PhenoAge时钟模型，通过血液生物标志物计算生物年龄的服务。
Based on the Morgan Levine PhenoAge clock model, the service calculates biological age through blood biomarkers.## 工具列表 Tool List

本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。 本MCP服务封装下列工具，可让模型通过标准化接口调用以下功能。

| 工具 Tool   | 描述 Description         |
|-------|--------------------|
| calculate_phenoage | Calculate biological age using the Morgan Levine PhenoAge clock based on blood biomarkers |
| get_biomarker_ranges | Get reference ranges and optimal values for PhenoAge biomarkers |


## 检查服务 ## Inspector

工具在线测试： [https://mcp.xiaobenyang.com/inspector/1777316659748867](https://mcp.xiaobenyang.com/inspector/1777316659748867)

Online Tool test [https://mcp.xiaobenyang.com/inspector/1777316659748867](https://mcp.xiaobenyang.com/inspector/1777316659748867)

## 服务配置 MCP Server Config


> #### 如何获取 XBY-APIKEY ？ How to get XBY-APIKEY ?
> 访问小笨羊科技网站 [https://xiaobenyang.com](https://xiaobenyang.com)，注册用户即可获得APIKEY
> Visit XiaoBenYang website [https://xiaobenyang.com](https://xiaobenyang.com), register and get the APIKEY.

### SSE
```json
{
  "mcpServers": {
    "生物年龄计算服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "sse",
      "url": "https://mcp.xiaobenyang.com/1777316659748867/sse"
    }
  }
}
```
### STREAMABLE HTTP
```json
{
  "mcpServers": {
    "生物年龄计算服务": {
      "headers": {
        "XBY-APIKEY": "<YOUR_XBY_APIKEY>"
      },
      "type": "streamable_http",
      "url": "https://mcp.xiaobenyang.com/1777316659748867/mcp"
    }
  }
}
```
### STDIO
```json
{
    "mcpServers": {
        "生物年龄计算服务": {
          "command": "npx",
          "args": [
            "-y",
            "xiaobenyang-mcp"
          ],
          "env": {
            "XBY_APIKEY": "<YOUR_XBY_APIKEY>",
            "mcpId": "1777316659748867",
          },
          "transport": "stdio"
        }
      }
}

```
