@echo off
title Limpeza de Arquivos Temporários

echo.
echo ===============================
echo  Limpando arquivos temporarios
echo ===============================
echo.

:: TEMP do usuario
del /f /s /q "%TEMP%\*" >nul 2>&1
for /d %%i in ("%TEMP%\*") do rd /s /q "%%i" >nul 2>&1

:: TEMP do Windows
del /f /s /q "C:\Windows\Temp\*" >nul 2>&1
for /d %%i in ("C:\Windows\Temp\*") do rd /s /q "%%i" >nul 2>&1

:: Limpeza de disco (se configurada)
cleanmgr /sagerun:1

echo.
echo Limpeza concluida com sucesso!
echo.
pause
