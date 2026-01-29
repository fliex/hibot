
使用说明
1. 基本用法（推荐使用 POST）
POST 请求支持直接使用中文，无需编码：

POST
https://hi.mauth.cn/api/send
{
  "key": "28512990",
  "title": "提醒标题",
  "message": "提醒内容"
}
复制 JSON
或者使用 GET 请求（浏览器会自动编码中文）：

GET
https://hi.mauth.cn/api/send?key=28512990&title=提醒标题&message=提醒内容
提示：浏览器会自动编码中文，服务器会自动解码
复制 URL复制 cURL
2. 参数说明
key - 您的 Sendkey（必需）
title - 提醒标题（必需）
message - 提醒内容（必需）
time - 提醒时间（可选，ISO格式，如：2026-01-31T18:00:00Z）
3. 示例代码
POST 方式（推荐，直接使用中文）
推荐
cURL
curl -X POST "https://hi.mauth.cn/api/send" \
  -H "Content-Type: application/json" \
  -d '{"key":"28512990","title":"测试提醒","message":"这是一条测试消息"}'
复制
JavaScript
fetch('https://hi.mauth.cn/api/send', {
  method: 'POST',
  headers: { 'Content-Type': 'application/json' },
  body: JSON.stringify({
    key: '28512990',
    title: '测试提醒',
    message: '这是一条测试消息'
  })
})
复制
Python
import requests
requests.post('https://hi.mauth.cn/api/send', json={
    'key': '28512990',
    'title': '测试提醒',
    'message': '这是一条测试消息'
})
复制
GET 方式（浏览器自动编码）
cURL
curl 'https://hi.mauth.cn/api/send?key=28512990&title=%E6%B5%8B%E8%AF%95%E6%8F%90%E9%86%92&message=%E8%BF%99%E6%98%AF%E4%B8%80%E6%9D%A1%E6%B5%8B%E8%AF%95%E6%B6%88%E6%81%AF'
复制
JavaScript
fetch('https://hi.mauth.cn/api/send?key=28512990&title=%E6%B5%8B%E8%AF%95%E6%8F%90%E9%86%92&message=%E8%BF%99%E6%98%AF%E4%B8%80%E6%9D%A1%E6%B5%8B%E8%AF%95%E6%B6%88%E6%81%AF')
复制
Python
import requests
requests.get('https://hi.mauth.cn/api/send', params={
    'key': '28512990',
    'title': '测试提醒',
    'message': '这是一条测试消息'
})
复制
4. 注意事项
同一用户并发请求不能超过 5 个
所有推送记录都会保存到通知日志中
需要先绑定微信公众号才能接收通知
Sendkey 请妥善保管，不要泄露给他人
