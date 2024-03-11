FROM mcr.microsoft.com/dotnet/sdk:8.0-alpine AS build
WORKDIR /app
EXPOSE 8080

COPY .. ./
RUN dotnet publish DomainA.Api/src/DomainA.Api.csproj -c Release -o out

FROM mcr.microsoft.com/dotnet/aspnet:8.0-alpine
WORKDIR /app
COPY --from=build /app/out .
ENTRYPOINT ["dotnet", "DomainA.Api.dll"]
