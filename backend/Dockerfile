# Stage 1: Build the .NET application
FROM mcr.microsoft.com/dotnet/sdk:10.0 AS build
WORKDIR /src
# Copy csproj and restore dependencies
COPY *.csproj ./
RUN dotnet restore
# Copy the rest of the code and publish
COPY . .
RUN dotnet publish -c Release -o /app/publish

# Stage 2: Run the application
FROM mcr.microsoft.com/dotnet/aspnet:10.0 AS runtime
WORKDIR /app
COPY --from=build /app/publish .

EXPOSE 8080 

# REPLACE 'YourBackendApp.dll' with the name of your .csproj file, but ending in .dll
ENTRYPOINT ["dotnet", "backend.dll"]