FROM pl31/miniconda3:jessie
MAINTAINER Patrick Büch <dh@paco.pl31.de>

COPY files/ /

RUN conda update --yes --quiet --all && \
    conda env update -n root -f ~/environment.yml && \
    conda clean --yes --tarballs && \
    conda env export -n root && \
    mkdir ~/notebooks

ENTRYPOINT ["jupyter", "notebook", "--no-browser", "--no-mathjax", "--ip=*", "/root/notebooks"]
