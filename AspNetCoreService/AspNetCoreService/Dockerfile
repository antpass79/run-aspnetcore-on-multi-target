#See https://aka.ms/containerfastmode to understand how Visual Studio uses this Dockerfile to build your images for faster debugging.

FROM mcr.microsoft.com/dotnet/aspnet:6.0 AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/sdk:6.0 AS build
WORKDIR /src
COPY ["AspNetCoreService/AspNetCoreService.csproj", "AspNetCoreService/"]
RUN dotnet restore "AspNetCoreService/AspNetCoreService.csproj"
COPY . .
WORKDIR "/src/AspNetCoreService"
RUN dotnet build "AspNetCoreService.csproj" -c Release -o /app/build

FROM build AS publish
RUN dotnet publish "AspNetCoreService.csproj" -c Release -o /app/publish

FROM base AS final
WORKDIR /app
COPY --from=publish /app/publish .
ENTRYPOINT ["dotnet", "AspNetCoreService.dll"]