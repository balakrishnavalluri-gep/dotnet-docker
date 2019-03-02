ARG REPO=mcr.microsoft.com/dotnet/core/runtime
FROM $REPO:3.0-stretch-slim-arm32v7

# Install ASP.NET Core
ENV ASPNETCORE_VERSION 3.0.0-preview3-19128-10

RUN curl -SL --output aspnetcore.tar.gz https://dotnetcli.blob.core.windows.net/dotnet/aspnetcore/Runtime/$ASPNETCORE_VERSION/aspnetcore-runtime-$ASPNETCORE_VERSION-linux-arm.tar.gz \
    && aspnetcore_sha512='7d0a6ea3c7922ed91b9bec06f0f22a245395d40a56206447a81e8617691c26389eaa9b85512949ff21dfe88e3bedc839266155688131f70c2c9884f507bb76b0' \
    && echo "$aspnetcore_sha512  aspnetcore.tar.gz" | sha512sum -c - \
    && tar -zxf aspnetcore.tar.gz -C /usr/share/dotnet ./shared/Microsoft.AspNetCore.App \
    && rm aspnetcore.tar.gz
