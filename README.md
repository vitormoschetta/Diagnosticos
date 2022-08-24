## Diagnóstico e Desempenho

#### Monitorar consumo de CPU por aplicação .NET

Instalar as seguintes ferramentas:
```
dotnet tool install --global dotnet-counters
dotnet tool install --global dotnet-trace
```

Executar um `trace` para pegar o ID dos processos .NET em execução:
```
dotnet-trace ps
```

Com o comando acima é possível identificar todas as aplicações .NET em execução, identificando pelo nome do Assembly.

Monitorar o consumo de CPU com o seguinte comando:
```
dotnet-counters monitor --refresh-interval 1 --counters System.Runtime[cpu-usage] -p <ID-PROCESSO>
```