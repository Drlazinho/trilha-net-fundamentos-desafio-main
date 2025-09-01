# Documentação do Sistema de Gerenciamento de Estacionamento

## Visão Geral

O Sistema de Gerenciamento de Estacionamento é uma aplicação de console desenvolvida em C# que permite o controle de veículos em um estacionamento. O sistema foi criado como parte do desafio da Trilha .NET Fundamentos da DIO.

## Arquitetura do Sistema

O projeto segue uma arquitetura simples, organizada da seguinte forma:

```
├── DesafioFundamentos/
│   ├── Models/
│   │   └── Estacionamento.cs    # Classe principal que gerencia o estacionamento
│   ├── Program.cs               # Ponto de entrada da aplicação e interface com o usuário
│   └── DesafioFundamentos.csproj
```

## Detalhamento das Classes

### Classe Estacionamento

A classe `Estacionamento` é responsável por toda a lógica de negócio do sistema. Ela contém os seguintes componentes:

#### Atributos

- `precoInicial` (decimal): Valor cobrado para estacionar o veículo, independente do tempo.
- `precoPorHora` (decimal): Valor cobrado por hora de permanência do veículo.
- `veiculos` (List<string>): Lista que armazena as placas dos veículos estacionados.

#### Construtor

```csharp
public Estacionamento(decimal precoInicial, decimal precoPorHora)
```

Inicializa uma nova instância da classe com os valores de preço inicial e preço por hora.

#### Métodos

##### AdicionarVeiculo()

```csharp
public void AdicionarVeiculo()
```

Solicita ao usuário a placa do veículo e a adiciona à lista de veículos estacionados. Realiza validação para garantir que a placa tenha 7 caracteres.

##### RemoverVeiculo()

```csharp
public void RemoverVeiculo()
```

Solicita ao usuário a placa do veículo a ser removido. Se o veículo estiver estacionado, solicita o número de horas que o veículo permaneceu no estacionamento e calcula o valor a ser pago (precoInicial + precoPorHora * horas).

##### ListarVeiculos()

```csharp
public void ListarVeiculos()
```

Exibe a lista de todos os veículos estacionados. Se não houver veículos, exibe a mensagem "Não há veículos estacionados".

### Programa Principal (Program.cs)

O arquivo `Program.cs` contém o ponto de entrada da aplicação e implementa a interface com o usuário através de um menu interativo. Ele realiza as seguintes operações:

1. Solicita ao usuário o preço inicial e o preço por hora.
2. Instancia a classe `Estacionamento` com os valores informados.
3. Exibe um menu com as opções disponíveis:
   - Cadastrar veículo
   - Remover veículo
   - Listar veículos
   - Encerrar
4. Executa a operação selecionada pelo usuário.
5. Repete o processo até que o usuário escolha encerrar o programa.

## Fluxo de Execução

1. O programa inicia solicitando o preço inicial e o preço por hora.
2. O menu principal é exibido com as opções disponíveis.
3. O usuário seleciona uma opção:
   - Se escolher "Cadastrar veículo", o sistema solicita a placa e a adiciona à lista.
   - Se escolher "Remover veículo", o sistema solicita a placa, verifica se o veículo está estacionado, solicita o tempo de permanência e calcula o valor a ser pago.
   - Se escolher "Listar veículos", o sistema exibe todos os veículos estacionados.
   - Se escolher "Encerrar", o programa é finalizado.
4. Após executar a operação selecionada, o sistema aguarda o usuário pressionar uma tecla para continuar e exibe o menu novamente.

## Como Executar o Projeto

1. Certifique-se de ter o .NET SDK instalado em seu computador.
2. Abra um terminal ou prompt de comando.
3. Navegue até o diretório do projeto (pasta que contém o arquivo .csproj).
4. Execute o comando: `dotnet run`
5. Siga as instruções exibidas no console.

## Considerações sobre o Código

- O sistema utiliza a codificação UTF8 para exibir corretamente caracteres acentuados.
- A validação da placa do veículo garante que ela tenha 7 caracteres.
- O sistema converte automaticamente as placas para maiúsculas para facilitar a comparação.
- Ao remover um veículo, o sistema valida se o número de horas informado é um valor numérico válido e maior ou igual a zero.

## Possíveis Melhorias

- Implementar persistência de dados para manter o registro dos veículos mesmo após o encerramento do programa.
- Adicionar validação mais robusta para o formato da placa do veículo.
- Implementar um sistema de relatórios para acompanhamento financeiro.
- Adicionar funcionalidade para reserva de vagas.
- Implementar um sistema de usuários com diferentes níveis de acesso.