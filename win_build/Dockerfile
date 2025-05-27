# 使用Windows基础镜像
FROM mcr.microsoft.com/windows/nanoserver:ltsc2022
# 安装Python和Cython
RUN powershell -Command "Invoke-WebRequest -Uri https://www.python.org/ftp/python/3.11.3/python-3.11.3.exe -OutFile python.exe; \
    Start-Process python.exe -ArgumentList '/quiet InstallAllUsers=1 PrependPath=1' -Wait; \
    pip install cython"

# 安装Visual Studio Build Tools（包含cl.exe）
RUN choco install visualstudio2022buildtools -y --package-parameters "--add Microsoft.VisualStudio.Workload.VCTools"
