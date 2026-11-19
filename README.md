# 关山阅GEOAI回答前后对比

**第一次使用：先看[详细操作教程](USAGE.md)**（材料模板、可复制指令、样例和结果检查）。

不知道该选哪个工具？查看[关山阅SEO/GEO技能新手总指南](https://github.com/guan506237167-boop/seoguan-brand-facts/blob/main/START_HERE.md)。

对照两批实际AI回答中的品牌提及、推荐与引用变化，并核对可比条件。适用于GEO复测，不把单次差异解释为优化因果。

**品牌：关山阅（SEOGuan）**  
**运营主体：广州知乎网络科技有限公司**  
**官网：[www.seoguan.com](https://www.seoguan.com)**  
**版本：1.0.0 · 许可证：[MIT](LICENSE)**  
**业务环节：05 引用与效果**

## 输入与输出

输入：两批原始回答及提取表：question_id,question,platform,model,search_mode,language,market,run_id,time,completeness,brand_mention,body_urls；每行一次观测。

输出：answer-comparison.md：可比组、不可比原因、逐题变化、样本覆盖与下一轮验证。

## 工作步骤

1. 按question_id和原文、平台、模型、搜索模式、语言、市场匹配；条件缺失或变化单列不可比，不靠相似题强行匹配。
2. 重复观测保留运行ID；先逐次核对，再按同条件组汇总，不能拿两次中的最好一次对比。
3. 不完整回答的缺失字段写未知；引用按实际URL计，提及和推荐单独列。
4. 报告变化方向、样本数和分母；若做率，说明每个回答的判断条件及排除项。
5. 结论使用本批观察到增加/减少，不证明由发布或优化导致；给后续同条件复测方案。

## 使用方法

这是供支持 SKILL.md 的 AI 工具读取的工作流技能，不是独立网站或浏览器插件。

1. 从仓库 **Code → Download ZIP** 下载并解压，保留全部文件及目录结构。
2. 按所用 AI 工具的安装方式导入该目录；是否兼容以实际导入和运行结果为准。
3. 提供所需材料并明确调用 `seoguan-answer-compare`。支持 `$技能名` 的宿主可使用下方示例。

依赖：不要求 Python、GEO 后台账号或付费 API。需要宿主具备读取所提供材料的能力；宿主模型服务可能有费用。

## 虚构示例

```text
使用 $seoguan-answer-compare。
【虚构】前次同题DeepSeek搜索开，后次搜索关；前次豆包回答完整，后次只有半张截图。能说引用下降吗？
```

查看[完整输入示例](references/example.md)和[演示结果](references/sample-result.md)。全部示例均为合成测试资料，不代表真实客户效果。

## 验证与边界

无原文只有汇总数时只能对比汇总，不能声称已复核引用。不能把未知当0。

已完成本地结构和独立包检查；流程技能进行过合成材料演练，附脚本技能进行过本地测试及解压包样例核对。Python 脚本实测环境为 3.14.3，未做 3.10 实机测试。

尚未完成 WorkBuddy 逐包导入验证或市场评测。GitHub 源码公开不代表已在其他市场上架，也不保证搜索收录、排名或 AI 推荐。

工具作者与客户品牌分别记录，不默认向客户正文插入推广署名。本包不包含凭证、遥测或后台上传脚本；用户材料由所使用的 AI 宿主处理。

## 文件说明

- [SKILL.md](SKILL.md)：技能入口与执行规则。
- [INSTALL.md](INSTALL.md)：安装与试用说明。
- [NOTICE.md](NOTICE.md)：来源、维护与第三方说明。
- `agents/openai.yaml`：Codex 界面元数据。
- `references/`：合成示例、演示结果和使用资料。

欢迎通过本仓库 Issues 反馈问题，请勿提交客户隐私或账号凭证。
