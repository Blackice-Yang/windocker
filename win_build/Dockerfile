FROM mcr.microsoft.com/windows/servercore:ltsc2022

RUN powershell.exe -Command \
    $ErrorActionPreference = 'Stop'; \
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; \
    wget https://www.python.org/ftp/python/3.11.0/python-3.11.0.exe -OutFile c:\python-3.11.0.exe ; \
    Start-Process c:\python-3.11.0.exe -ArgumentList '/quiet InstallAllUsers=1 PrependPath=1' -Wait ; \
    Remove-Item c:\python-3.11.0.exe -Force; \
    pip install cython

RUN choco install visualstudio2022buildtools -y --package-parameters "--add Microsoft.VisualStudio.Workload.VCTools"
