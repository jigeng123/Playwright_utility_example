# Playwright_utility_example
常用的playwright示例
#需要配置环境
安装python和pip
pip install playwright
playwright install
#官方文档：
🔗 https://playwright.dev/python/
#常用操作
```
print("Hello, world!")
for i in range(3):
print(i)
```
最简单的例子（无窗口运行）
'''
from playwright.sync_api import sync_playwright

with sync_playwright() as p:
    browser = p.chromium.launch(headless=True)  # 无头模式（不显示窗口）
    page = browser.new_page()
    page.goto("https://example.com")  # 访问网页
    print("网页标题：", page.title())
    print("页面中 h1 文本：", page.text_content("h1"))
    browser.close()
'''
| 功能        | 示例代码                                |
| --------- | ----------------------------------- |
| 打开网页      | `page.goto("https://...")`          |
| 获取标题      | `page.title()`                      |
| 获取文本      | `page.text_content("css选择器")`       |
| 点击按钮      | `page.click("css选择器")`              |
| 输入文本      | `page.fill("输入框选择器", "你好")`         |
| 截图        | `page.screenshot(path="page.png")`  |
| 等待元素出现    | `page.wait_for_selector("css选择器")`  |
| 获取多个元素内容  | `page.query_selector_all("css选择器")` |
| 使用无头/有头模式 | `headless=True` / `False`           |
