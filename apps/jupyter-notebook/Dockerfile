FROM jupyter/minimal-notebook:latest

RUN pip install --no-cache-dir openai langchain && \
    fix-permissions "${CONDA_DIR}" && \
    fix-permissions "/home/${NB_USER}"

EXPOSE 8888
CMD ["start.sh", "jupyter", "lab", "--LabApp.token=''"]
