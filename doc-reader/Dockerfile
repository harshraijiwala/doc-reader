FROM pytorchlightning/pytorch_lightning:base-cuda-py3.9-torch1.12
RUN pip install -U pip
EXPOSE 8501
WORKDIR /ocrcv
COPY requirements.txt .
RUN pip install -r requirements.txt
ENV OPENAI_API_KEY=<YOUR_API_KEY>
COPY app.py background.jpg sidebar.jpg .
ENTRYPOINT [ "streamlit", "run" ]
CMD [ "app.py", "--server.headless", "true", "--server.fileWatcherType", "none", "--browser.gatherUsageStats", "false"]
