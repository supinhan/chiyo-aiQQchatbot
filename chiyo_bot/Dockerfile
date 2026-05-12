FROM python:3.10-slim
WORKDIR /app
# 离线安装所有必要的 Python 库
RUN pip install --no-cache-dir nonebot2[fastapi] nonebot-adapter-onebot pydantic jieba tavily-python openai python-dotenv datetime
COPY . .
# 强制清理 Windows 传过来的编译缓存，防止环境冲突
RUN find . -name "__pycache__" -type d -exec rm -rf {} +
CMD ["nb", "run"]
