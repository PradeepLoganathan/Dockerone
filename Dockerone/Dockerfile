#layer 1
#MAINTAINER Pradeep Loganathan<pradeep@pradeeploganathan.com>

FROM microsoft/dotnet:2.1-sdk AS builder
WORKDIR /app
RUN cd
COPY *.csproj ./
RUN dotnet restore
COPY . ./

FROM builder as publisher
RUN cd
RUN dir 
RUN dotnet publish -c Release -o app2
RUN dir 

FROM microsoft/dotnet:2.1-runtime AS prod
WORKDIR /app
RUN cd
RUN dir
copy --from=publisher /app/app2 ./
RUN dir
ENTRYPOINT ["dotnet", "dockerone.dll"]

