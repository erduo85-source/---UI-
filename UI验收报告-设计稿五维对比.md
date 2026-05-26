# 国内游卡账号中心 UI 验收报告 - 设计稿五维对比

验收日期：2026-05-26

验收范围：桌面端单视口；不包含登录保护、登录设备、登录锁定、安全防护等三期能力。

设计依据：

- Figma 文件：[国内 游卡账号中心](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=42603-155)
- 已保存设计参考图：[账号中心参考图](pic/figma-account-center-reference.png)，对应参考 frame：[node 44163-1879](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1879)
- 节点索引：`设计稿节点列表.md`

线上环境：

- 地址：`https://account-test.yokaverse.com/`
- 当前账号状态：已登录、已实名、登录手机已绑定、安全手机已绑定、安全邮箱未绑定、登录密码已设置。
- 当前可见手机号脱敏值：`152****9728`。

验收口径：

- 按 `ui-design-qa` skill 核对文案、图标、颜色、间距、字体五个维度。
- 状态仅使用：`通过`、`不通过`、`未验证`。
- 文案不一致、图标缺失或多余可直接判定问题；颜色差异大于 5 个 hex unit、间距差异达到 2px、字号差异达到 2px、字重差异达到 100、行高差异达到 3px 时判定问题。
- 本轮 Chrome 页面截图与 computed style 已重新获取；但当前会话未暴露可调用的 Figma MCP 精确样式读取接口，因此颜色、间距、字体的像素级 token 差异不伪判通过，无法精确核对的条目标为 `未验证`。
- 本报告为独立 UI 对比报告，不改写 `全量验收清单.md` 的历史功能结论。

## 结果汇总

| 项目 | 数量 |
| --- | ---: |
| 已识别设计/交互状态 | 34 |
| 不通过 | 4 |
| 未验证 | 30 |
| 已保存本轮线上截图 | 16 |

## 设计状态覆盖表

| 序号 | 模块 | 页面/状态 | 线上进入路径 | Figma 节点链接 | 是否可触达 | 验收结果 | 未验证原因/备注 |
| ---: | --- | --- | --- | --- | --- | --- | --- |
| 1 | 账号中心 | 首页整体与页头 | 登录后访问 `/` | [首页](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=42603-155) | 是 | 不通过 | 页头品牌文案与已保存设计参考图不一致，见问题 P-001 |
| 2 | 账号中心 | 账号信息卡片 | `/` 默认页签 | [账号信息](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1939) | 是 | 未验证 | 已截图；精确设计 token 本轮未能重新拉取 |
| 3 | 账号中心 | 安全信息区块 | `/` 首页下半区 | [安全信息](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1945) | 是 | 未验证 | 已截图；精确设计 token 本轮未能重新拉取 |
| 4 | 账号信息 | 实名认证查看弹窗 | 首页点击“已实名” | [账号信息](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1939) | 是 | 未验证 | 弹窗可展示姓名、身份证；缺精确弹窗节点数据 |
| 5 | 登录手机 | 已绑定展示态 | 首页查看登录手机行 | [登录手机](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-2049) | 是 | 未验证 | 当前展示 `152****9728` 与“换绑”；设计参考截图为未绑定态 |
| 6 | 登录手机 | 未绑定展示态 | 需未绑定登录手机账号 | [登录手机](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-2049) | 否 | 未验证 | 当前账号已绑定登录手机 |
| 7 | 登录手机 | 换绑中展示态 | 需已提交换绑的账号状态 | [登录手机](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-2049) | 否 | 未验证 | 尚未提交真实换绑 |
| 8 | 登录手机 | 换绑安全验证弹窗 | 登录手机行点击“换绑” | [登录手机](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-2049) | 是 | 未验证 | 弹窗显示“安全验证/登录手机”；缺对应精确设计节点 |
| 9 | 登录手机 | 发送验证码前置行为验证 | 换绑安全验证点击“发送” | [登录手机](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-2049) | 是 | 未验证 | 已出现滑块验证层；需人工完成后才能继续短信与后续表单 |
| 10 | 登录手机 | 换绑新手机号表单 | 通过安全验证后进入 | [登录手机](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-2049) | 否 | 未验证 | 当前阻塞于行为验证与短信验证码 |
| 11 | 登录手机 | 换绑成功/换绑中详情 | 提交第二手机号换绑后进入 | [登录手机](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-2049) | 否 | 未验证 | 执行需第二手机号、验证码及真实状态变更 |
| 12 | 登录密码 | 修改密码安全验证弹窗 | 登录密码行点击“修改” | [登录密码](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1989) | 是 | 未验证 | 已截图；缺对应精确弹窗节点数据 |
| 13 | 登录密码 | 新密码表单 | 修改密码安全验证通过后进入 | [登录密码](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1989) | 否 | 未验证 | 需安全验证码 |
| 14 | 登录密码 | 修改成功与重新登录 | 提交新密码后进入 | [登录密码](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1989) | 否 | 未验证 | 需新密码策略及重新登录凭据 |
| 15 | 安全手机 | 已绑定展示态 | 首页查看安全手机行 | [安全手机](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1988) | 是 | 未验证 | 当前展示 `152****9728` 与“换绑”；缺精确设计 token |
| 16 | 安全手机 | 未绑定展示态 | 需未绑定安全手机账号 | [安全手机](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1988) | 否 | 未验证 | 当前账号已绑定安全手机 |
| 17 | 安全手机 | 换绑安全验证弹窗 | 安全手机行点击“换绑” | [安全手机](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1988) | 是 | 不通过 | 弹窗展示旧术语“更换密保手机/认证手机”，见问题 P-002 |
| 18 | 安全手机 | 换绑新手机号及完成态 | 安全验证并提交后进入 | [安全手机](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1988) | 否 | 未验证 | 需安全验证码、第二手机号与真实状态变更 |
| 19 | 安全邮箱 | 未绑定展示态 | 首页查看安全邮箱行 | [安全邮箱](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1994) | 是 | 未验证 | 当前展示绑定入口；精确样式值未读取 |
| 20 | 安全邮箱 | 绑定入口弹窗 | 安全邮箱行点击“绑定” | [安全邮箱](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1994) | 是 | 不通过 | 未进入安全邮箱绑定流程，弹出错误引导，见问题 P-003 |
| 21 | 安全邮箱 | 邮箱填写/验证码表单 | 安全验证或绑定入口后进入 | [安全邮箱](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1994) | 否 | 未验证 | 当前入口流转异常，无法输入 Gmail 地址 |
| 22 | 安全邮箱 | 已绑定/换绑/成功态 | 成功绑定邮箱后进入 | [安全邮箱](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1994) | 否 | 未验证 | 因入口异常未到填写环节，未向 Gmail 发送验证码 |
| 23 | FAQ | FAQ 弹窗及默认展开内容 | 点击浮动“常见问题”按钮 | [公共页面参考](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=43966-2277) | 是 | 不通过 | 缺少二期登录手机与安全手机差异问题，见问题 P-004 |
| 24 | 账号服务 | 安全中心入口页 | 点击顶部“账号服务” | [账号服务](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1893) | 是 | 未验证 | 本轮页面已加载四类服务入口；缺精确设计节点对照值 |
| 25 | 密码重置 | 初始账号填写页 | 访问 `/password` | [账号服务](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1893) | 是 | 未验证 | 页面已正常加载；空值时确认按钮为禁用态 |
| 26 | 账号找回 | 安全手机方式 | 访问 `/passport` 默认态 | [账号服务](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1893) | 是 | 未验证 | 已截图；缺精确设计节点对照值 |
| 27 | 账号找回 | 安全邮箱方式 | `/passport` 选择“安全邮箱” | [账号服务](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1893) | 是 | 未验证 | 已截图；页面字段显示“邮箱号”，待精确设计节点复核 |
| 28 | 账号找回 | 充值订单方式 | `/passport` 选择“充值订单” | [账号服务](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1893) | 是 | 未验证 | 已截图；缺精确设计节点对照值 |
| 29 | 账号申诉 | 申诉条款与入口页 | 访问 `/security/appeal` | [账号服务](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1893) | 是 | 未验证 | 已截图；未提交申诉 |
| 30 | 异常页 | 页面加载失败态 | 需构造失败路由或异常响应 | [页面异常](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=43966-2277) | 否 | 未验证 | 本轮 `/password`、`/passport` 已恢复正常加载，未强行构造异常 |
| 31 | 输入校验 | 登录手机/安全手机空值与格式态 | 进入对应变更表单后触发 | [登录手机](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-2049) | 否 | 未验证 | 阻塞于安全验证步骤 |
| 32 | 输入校验 | 安全邮箱空值与格式态 | 进入邮箱绑定表单后触发 | [安全邮箱](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1994) | 否 | 未验证 | 安全邮箱绑定入口流转异常 |
| 33 | 成功反馈 | 强制登出类成功弹窗 | 完成登录手机绑定或修改密码 | [登录密码](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1989) | 否 | 未验证 | 尚未取得安全验证与变更数据 |
| 34 | 成功反馈 | 普通成功弹窗 | 完成安全手机或安全邮箱绑定 | [安全邮箱](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1994) | 否 | 未验证 | 尚未进入可提交绑定的表单 |

## 五维对比明细表

| 序号 | 模块 | 页面/状态 | 文案 | 图标 | 颜色 | 间距 | 字体 | 综合结果 | 线上截图 | 设计稿截图 | Figma 链接 | 备注 |
| ---: | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| 1 | 账号中心 | 首页整体与页头 | 不通过 | 未验证 | 未验证 | 未验证 | 未验证 | 不通过 | [线上](pic/uiqa-account-home-current.png) | [设计](pic/figma-account-center-reference.png) | [首页](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=42603-155) | 线上页头未展示设计图可见的“账号中心”品牌文案 |
| 2 | 账号中心 | 账号信息与安全信息区块 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | [线上](pic/uiqa-account-home-current.png) | [设计](pic/figma-account-center-reference.png) | [账号信息](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1939) | 当前账号状态与设计参考图的登录手机状态不同，不混判 |
| 3 | 账号信息 | 实名认证查看弹窗 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | [线上](pic/uiqa-realname-dialog-current.png) | 无 | [账号信息](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1939) | 可见“实名认证/姓名/身份证/确认”，未获取精确弹窗设计节点 |
| 4 | 登录手机 | 换绑安全验证弹窗 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | [线上](pic/uiqa-login-phone-change-verification.png) | 无 | [登录手机](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-2049) | 可见登录手机脱敏号码及验证码输入 |
| 5 | 登录手机 | 发送验证码行为验证层 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | [线上](pic/uiqa-login-phone-verification-after-send.png) | 无 | [登录手机](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-2049) | 点击发送后出现滑块行为验证，短信尚未实际发送 |
| 6 | 登录密码 | 修改密码安全验证弹窗 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | [线上](pic/uiqa-password-change-verification.png) | 无 | [登录密码](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1989) | 可见“登录密码/手机验证/下一步” |
| 7 | 安全手机 | 换绑安全验证弹窗 | 不通过 | 未验证 | 未验证 | 未验证 | 未验证 | 不通过 | [线上](pic/uiqa-security-phone-change-verification.png) | 无 | [安全手机](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1988) | 弹窗采用“密保手机/认证手机”旧术语 |
| 8 | 安全邮箱 | 未绑定状态点击绑定 | 不通过 | 未验证 | 未验证 | 未验证 | 未验证 | 不通过 | [线上](pic/uiqa-security-email-bind-verification.png) | 无 | [安全邮箱](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1994) | 未进入邮箱绑定弹窗，错误提示登录手机需绑定 |
| 9 | FAQ | 常见问题弹窗 | 不通过 | 未验证 | 未验证 | 未验证 | 未验证 | 不通过 | [线上](pic/uiqa-faq-dialog-current.png) | 无 | [公共页面参考](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=43966-2277) | 列表未展示登录手机与安全手机差异 FAQ |
| 10 | 账号服务 | 安全中心入口页 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | [线上](pic/uiqa-account-service-navigation.png) | 无 | [账号服务](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1893) | 当前已可见账号申诉、通行证找回、密码重置、咨询客服 |
| 11 | 密码重置 | 初始账号填写页 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | [线上](pic/uiqa-route-password.png) | 无 | [账号服务](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1893) | 本轮正常加载，空值确认按钮为 disabled |
| 12 | 账号找回 | 安全手机方式 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | [线上](pic/uiqa-passport-phone-method.png) | 无 | [账号服务](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1893) | 默认选中安全手机 |
| 13 | 账号找回 | 安全邮箱方式 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | [线上](pic/uiqa-passport-email-method.png) | 无 | [账号服务](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1893) | 线上字段文案为“邮箱号”，待设计节点精确核对 |
| 14 | 账号找回 | 充值订单方式 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | [线上](pic/uiqa-passport-order-method.png) | 无 | [账号服务](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1893) | 可见充值游戏与商户订单号字段 |
| 15 | 账号申诉 | 条款与入口页 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | 未验证 | [线上](pic/uiqa-route-appeal.png) | 无 | [账号服务](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1893) | 未提交申诉 |

## 问题清单

| 序号 | 模块 | 页面/状态 | 问题维度 | 问题 | 线上效果 | 期望效果 | 问题截图 | 对应设计稿链接 | 备注 |
| ---: | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| P-001 | 账号中心 | 首页页头 | 文案 | 页头缺少账号中心品牌标题 | 页头左侧仅可见游卡 LOGO，未展示“账号中心”标题 | 按设计参考图展示“游卡 \| 账号中心”品牌标题 | [线上](pic/uiqa-account-home-current.png) / [设计](pic/figma-account-center-reference.png) | [首页](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=42603-155) | 可由已有设计截图直接判定 |
| P-002 | 安全手机 | 换绑安全验证弹窗 | 文案 | 安全手机换绑弹窗沿用旧术语 | 点击安全手机“换绑”后显示“更换密保手机”“认证手机” | 使用设计/需求统一术语“安全手机”及相应安全验证文案 | [截图](pic/uiqa-security-phone-change-verification.png) | [安全手机](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1988) | 与页面主信息项“安全手机”术语不一致 |
| P-003 | 安全邮箱 | 未绑定状态点击“绑定” | 文案/交互态 | 安全邮箱绑定入口进入错误提示弹窗 | 首页已展示登录手机 `152****9728`，点击安全邮箱“绑定”后却弹出“账号已换绑安全手机，建议您绑定登录手机”的温馨提示 | 进入安全邮箱绑定/安全验证流程，展示安全邮箱相关表单或验证弹窗 | [截图](pic/uiqa-security-email-bind-verification.png) | [安全邮箱](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=44163-1994) | 阻断安全邮箱后续 UI 状态验证，尚未发送邮件验证码 |
| P-004 | FAQ | 常见问题弹窗 | 文案 | 缺少登录手机二期 FAQ 项 | 当前列表未出现“登录手机和安全手机有什么区别？” | 展示登录手机与安全手机差异的 FAQ 项及答案 | [截图](pic/uiqa-faq-dialog-current.png) | [公共页面参考](https://www.figma.com/design/zdbqXSiRNRL373XDbQSnht/%E5%9B%BD%E5%86%85-%E6%B8%B8%E5%8D%A1%E8%B4%A6%E5%8F%B7%E4%B8%AD%E5%BF%83?node-id=43966-2277) | 同时有需求文档二期内容依据 |

## 本轮截图证据

| 序号 | 页面/状态 | 截图 |
| ---: | --- | --- |
| 1 | 账号中心首页当前态 | [uiqa-account-home-current.png](pic/uiqa-account-home-current.png) |
| 2 | 实名认证查看弹窗 | [uiqa-realname-dialog-current.png](pic/uiqa-realname-dialog-current.png) |
| 3 | 登录手机换绑安全验证 | [uiqa-login-phone-change-verification.png](pic/uiqa-login-phone-change-verification.png) |
| 4 | 登录手机发送验证码后的行为验证层 | [uiqa-login-phone-verification-after-send.png](pic/uiqa-login-phone-verification-after-send.png) |
| 5 | 修改密码安全验证 | [uiqa-password-change-verification.png](pic/uiqa-password-change-verification.png) |
| 6 | 安全手机换绑安全验证 | [uiqa-security-phone-change-verification.png](pic/uiqa-security-phone-change-verification.png) |
| 7 | 安全邮箱绑定入口异常提示 | [uiqa-security-email-bind-verification.png](pic/uiqa-security-email-bind-verification.png) |
| 8 | FAQ 弹窗 | [uiqa-faq-dialog-current.png](pic/uiqa-faq-dialog-current.png) |
| 9 | 账号服务入口页 | [uiqa-account-service-navigation.png](pic/uiqa-account-service-navigation.png) |
| 10 | 密码重置页 | [uiqa-route-password.png](pic/uiqa-route-password.png) |
| 11 | 密码重置空值初始态 | [uiqa-password-empty-validation.png](pic/uiqa-password-empty-validation.png) |
| 12 | 通行证找回初始页 | [uiqa-route-passport.png](pic/uiqa-route-passport.png) |
| 13 | 账号找回 - 安全手机方式 | [uiqa-passport-phone-method.png](pic/uiqa-passport-phone-method.png) |
| 14 | 账号找回 - 安全邮箱方式 | [uiqa-passport-email-method.png](pic/uiqa-passport-email-method.png) |
| 15 | 账号找回 - 充值订单方式 | [uiqa-passport-order-method.png](pic/uiqa-passport-order-method.png) |
| 16 | 账号申诉入口页 | [uiqa-route-appeal.png](pic/uiqa-route-appeal.png) |

## 阻塞与后续可继续项

- 登录手机换绑验证码流程已触发行验证滑块，当前没有实际发送短信；完成滑块并提供短信验证码后，可继续核对换绑新手机号表单与后续状态。
- 安全邮箱“绑定”入口当前进入错误提示弹窗，尚未到可输入 Gmail 地址或发送邮件验证码的步骤，因此未读取 Gmail 邮件。
- 颜色、间距、字体的像素级量化对比需恢复可调用的 Figma 精确样式/截图接口后继续补验。
