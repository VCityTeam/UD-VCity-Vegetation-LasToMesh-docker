FROM python:3.9.17-bullseye

LABEL maintainer "VCityTeam"
LABEL source.repo "https://github.com/VCityTeam/UD-VCity-Vegetation-LasToMesh-docker.git"

# Assert that python3 is installed
RUN python3 --version

# Install build libraries
RUN apt-get install -y  git

# Clone sources from release branch
RUN git clone https://github.com/VCityTeam/UD-VCity-Vegetation-LasToMesh.git
WORKDIR /UD-VCity-Vegetation-LasToMesh
RUN pip install -r requirements.txt

# Install Open3D system dependencies, refer to
# http://www.open3d.org/docs/release/docker.html#install-and-run-open3d-apps-in-docker
RUN apt-get update && apt-get install --no-install-recommends -y \
  libegl1 \
  libgl1 \
  libgomp1 \
  && rm -rf /var/lib/apt/lists/*

# Arguments for the execution
ENV FILE_NAME=${FILE_NAME}
ENV CELL_SIZE=${CELL_SIZE}
ENV VERBOSE=${VERBOSE}

CMD  [ "sh", "-c", "python3.9 mainCLI.py -i /inputs/${FILE_NAME} -o /outputs/ -c ${CELL_SIZE} ${VERBOSE}"]
