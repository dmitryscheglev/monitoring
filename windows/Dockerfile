FROM 	microsoft/windowsservercore:10.0.14393.2068

ENV		USERNAME admin

RUN		net user %USERNAME% /ADD && \
		net localgroup administrators %USERNAME% /add

USER	admin 

RUN		whoami && \
		powershell -NoProfile -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && \
		SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin" && \
		cinst -y 7zip.portable git && \
		refreshenv && \
		git config --global http.sslVerify "false"
