#Zad3.
#budowanie obrazu
docker build -f Dockerfile_z1 -t local/zad1:v1 .


#ruchamianie kontenera na podstawie zbudowanego obrazu
docker run -t -d --name "zad1" -p 1010:81/tcp local/zad1:v1

#wyswietlenie warstw obrazu
docker image inspect local/zad1:v1

#Zad4.
docker login -u krystynakornas -p

docker buildx build -f Dockerfile_z1 -t krystynakornas/zad1:v1 --platform linux/arm64,linux/amd64,linux/ppc64le,linux/arm/v7 --push .
