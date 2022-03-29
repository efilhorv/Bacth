# Bacth
@echo off
rem abaixo temos o padrão de configuração de mês e ano sendo mydatey o ano, mydatem o mês e mydated o dia

set mydatey=%date:~6,4%
set mydatem=%date:~3,2%
set mydated=%date:~0,2%

rem abaixo está sendo criando uma sentença para o mês e pode ser replicada para ano ou dia
rem e está sendo realizado a definição o valor do mês atual para ser o mês anterior

if %mydatem%==01 set mydatem=12
if %mydatem%==02 set mydatem=01
if %mydatem%==03 set mydatem=02
if %mydatem%==04 set mydatem=03
if %mydatem%==05 set mydatem=04
if %mydatem%==06 set mydatem=05
if %mydatem%==07 set mydatem=06
if %mydatem%==08 set mydatem=07
if %mydatem%==09 set mydatem=08
if %mydatem%==10 set mydatem=09
if %mydatem%==11 set mydatem=10
if %mydatem%==12 set mydatem=11

set mydate=%mydatey%%mydatem%%mydated%

rem é assim que ficara a variavel mydate 20220229
rem abaixo um exemplo de usualidade para extração do arquivo com o nome variavel dia a dia que na data da contrução é BASE_XXXX_20220229.zip
rem caso queira ver como está a sua variavel mydate é só colocar "echo mydate" abaixo do último set
rem lembrando que esté bate é para o mes anterior devido as definições acima se não precisar e for o mes atual é só remover todos os if

rem pode remover todos os rem se quiser e lembrese de salvar como .bat

7z e -y M:\ARQUIVOS_ORIGINAIS\BASES_FONTE\BASE_XXXX_%mydate%.zip

rem o mesmo será extraido na pasta que está o bat
exit
