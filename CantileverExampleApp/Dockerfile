FROM mcr.microsoft.com/dotnet/aspnet:5.0
COPY bin/Release/net5.0/publish/ CantileverExampleApp/
WORKDIR /CantileverExampleApp
ENTRYPOINT ["dotnet", "CantileverExampleDocker.Docker.dll"]