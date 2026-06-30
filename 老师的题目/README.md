# 文档智能处理系统

这是一个基于 Streamlit 的文档智能处理小工具，支持多用户注册登录、用户文件隔离、PDF/Word/图片/扫描版 PDF 上传解析、OCR 识别、摘要生成、词频统计可视化和自动分类。

## 功能

- 多用户：支持注册、登录、退出登录。
- 用户隔离：每个用户只能看到自己账号上传过的文档历史。
- 文件解析：支持 PDF、DOCX、PNG、JPG、JPEG、BMP、TIF、TIFF。
- OCR：普通图片和扫描版 PDF 使用 Tesseract OCR 识别文本。
- 文本摘要：基于词频和句子打分生成抽取式摘要。
- 词频统计：展示高频词柱状图和词云。
- 文件分类：基于关键词规则自动判断文档类别。
- 公网访问：可部署到 Streamlit Community Cloud。

## 本地运行

```bash
pip install -r requirements.txt
streamlit run app.py
```

Windows 本地如需使用 OCR，请先安装 Tesseract OCR，并确保命令行中可以执行 `tesseract`。

## 云端部署

1. 将本项目上传到 GitHub。
2. 打开 Streamlit Community Cloud：https://share.streamlit.io/
3. 选择该 GitHub 仓库。
4. Main file path 填写 `app.py`。
5. 点击 Deploy，部署成功后即可获得公网访问链接。

`packages.txt` 已声明云端 OCR 所需系统依赖：

```txt
tesseract-ocr
tesseract-ocr-chi-sim
poppler-utils
```

## 数据说明

程序运行时会自动创建：

```text
data/app.db          用户、文档记录数据库
data/uploads/        每个用户上传的原始文件
```

这些运行时数据不会提交到 GitHub。部署后新用户可在网页中自行注册账号并上传文档。

## 交付说明

- 代码仓库：部署前填写 GitHub 仓库链接。
- 公网访问链接：部署成功后填写 Streamlit 应用链接。
- 技术栈：Python、Streamlit、SQLite、PyMuPDF、python-docx、pytesseract、pdf2image、jieba、Plotly、WordCloud。
