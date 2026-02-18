# Use Python 3.10 with Debian Buster as the base image
FROM python:3.10-buster

# Set the working directory inside the container
WORKDIR /app


# Clone the repositories
RUN git clone -b dev https://github.com/DiamondLightSource/fast_rsm.git && \
    git clone -b dev https://github.com/DiamondLightSource/diffraction_utils.git && \
    git clone -b dev https://github.com/DiamondLightSource/mapper_c_utils.git

RUN CFLAGS="-std=c99"\
    #pip install notebook --only-binary=:all: && \
    pip install pyFAI --only-binary=:all: && \
    #pip install spyder-kernels==2.5.* && \
    pip install pyopencl --only-binary=:all: && \
    pip install -r ./fast_rsm/requirements.txt && \
    pip install -r ./diffraction_utils/requirements.txt && \
    pip install setuptools==73.0.1 && \
    pip install siphash24 && \
    pip install --no-build-isolation mapper_c_utils/&& \
    pip install fast_rsm/ && \
    #pip install jupyter_contrib_nbextensions && \
    pip install --use-pep517 diffraction_utils/


#RUN parse_template < fast_rsm_diamond_config/Scripts/runconfig.template > fast_rsm/CLI/i07/runconfig.py

# Default command: Open a shell for flexibility
CMD ["bash"]

