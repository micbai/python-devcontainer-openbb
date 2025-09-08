FROM continuumio/miniconda3

WORKDIR /app

COPY environment.yml .

RUN conda update -n base conda -y && \
    conda env create -f environment.yml && \
    conda clean -a -y

SHELL ["conda", "run", "-n", "openbb-env", "/bin/bash", "-c"]

EXPOSE 8888

CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888", "--no-browser", "--allow-root", "--NotebookApp.token=''"]