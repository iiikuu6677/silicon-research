# 芯研 AI · 半导体研究终端

中文版响应式 MVP，基于 React 19、TypeScript、Vite 和 Tailwind CSS 4。适合 iPad、手机与电脑。

## 已实现
- 总览：七个研究标的、分类筛选、名称/代码搜索、示例市场趋势。
- 公司研究：商业模式、产品、竞争优势、风险和示例估值。
- 财务分析：六家公司切换，营收/净利润/毛利率/自由现金流四年示例图。
- 技术分析：合成 K 线及均线演示；RSI/MACD/成交量占位。
- 产业链：概念关系与可点击公司节点。
- QQQ：指数介绍、示例持仓及集中度、风险和基金官网链接。
- 投资笔记：浏览器本地保存、状态更新、删除和 JSON 导出。

## 数据说明
所有行情、图表、财务、估值、收益及持仓权重都是虚构演示数据，没有接入行情接口。SKHY 是平台内部研究简称，SK hynix 韩国上市代码为 KRX:000660，演示报价使用韩元。图表不是投资信号。公司文字是业务概括，产业关系不是已核实合同。
投资笔记仅保存在当前浏览器 localStorage，不跨设备同步；请定期导出 JSON。免费托管不会自动提供数据库。

## iPad 云端预览与免费部署（无需本地安装）
1. 在 Safari 打开 https://github.com ，注册/登录账号，点击 + → New repository，名称建议 silicon-research，创建仓库。
2. 解压源码包，在仓库 Add file → Upload files 上传源码（包含 src 文件夹、package.json、package-lock.json、index.html、tsconfig.json 和 vite.config.ts；不要上传 node_modules）。iPad 上传目录不方便时，可在 Codespaces 中上传源码压缩包后解压到仓库根目录。
3. 仓库 Code → Codespaces → Create codespace on main。Codespaces 有个人免费额度，结束使用后停止环境以节省额度。
4. 打开终端，运行 npm ci，然后 npm run dev。在 Ports 中打开 5173 的浏览器预览链接。
5. 免费静态部署可用 Cloudflare Pages：登录 https://dash.cloudflare.com ，Workers & Pages → Create → Pages → Connect to Git，授权所选 GitHub 仓库。框架选 Vite，构建命令 npm run build，输出目录 dist。成功后获取 https://项目名.pages.dev 分享地址；提交源码可触发更新。免费方案及限制以服务商当时政策为准。
6. 无需 GitHub 的部署：在 Cloudflare Pages 选择 Direct Upload，新建项目并上传发布包（dist 文件的压缩包）。完成后同样得到 pages.dev 地址。

## 开发命令
npm ci
npm run dev
npm run build

## 下一阶段
接入有授权的行情/财报 API、实现真实指标计算、添加笔记云同步和来源/更新时间。API 密钥只能放服务端，不能写入浏览器代码。

## 验证范围
构建包含 TypeScript 严格类型检查。当前云端没有提供可用的 Sites 发布辅助脚本或用户浏览器预览通道，因此未通过 Sites 发布或完成 iPad 真机验证；发布包可直接上传静态托管。
