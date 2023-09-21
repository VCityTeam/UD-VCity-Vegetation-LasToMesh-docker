# UD-VCity-Vegetation-LasToMesh-docker
Containerization of the Vegetation-LasToMesh application

### Installation

Without installing the sources _without_ cloning a repository

```bash
docker build -t vegetation-lastomesh https://github.com/VCityTeam/UD-VCity-Vegetation-LasToMesh-docker.git#:Context
```

You can achieve the same result _with_ a repository cloning

```bash
git clone https://github.com/VCityTeam/UD-VCity-Vegetation-LasToMesh-docker.git
cd UD-VCity-Vegetation-LasToMesh-docker
docker build -t vegetation-lastomesh ./Context
```

### Usage

You can run vegetation-lastomesh on the sample datas that are provided with
the application. This goes

```bash
git clone git@github.com:VCityTeam/UD-VCity-Vegetation-LasToMesh.git
cd UD-VCity-Vegetation-LasToMesh/SampleDatas
mkdir outputs
docker run -v $(pwd):/inputs -v $(pwd):/outputs vegetation-lastomesh -c 2.0 --input /inputs/ExampleDataDenseVegetation.las -o /outputs/outputs/
```