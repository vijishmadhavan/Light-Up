 FROM python:3.7

WORKDIR /enhance

COPY requirements.txt ./requirements.txt

RUN pip3 install -r requirements.txt

EXPOSE 8501

COPY . /enhance

ENTRYPOINT ["streamlit","run"]

CMD ["Good.py"]