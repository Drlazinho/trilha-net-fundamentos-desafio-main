# Sistema de Gerenciamento de Estacionamento

## Descrição
Este projeto é um sistema simples de gerenciamento de estacionamento desenvolvido em C# como parte da Trilha .NET Fundamentos da DIO. O sistema permite gerenciar veículos estacionados, realizar operações como adicionar e remover veículos, além de listar os veículos presentes no estacionamento.

## Funcionalidades

- **Cadastrar Veículo**: Adiciona um novo veículo ao estacionamento através da placa.
- **Remover Veículo**: Remove um veículo do estacionamento e calcula o valor a ser pago com base no tempo de permanência.
- **Listar Veículos**: Exibe todos os veículos atualmente estacionados.
- **Encerrar**: Finaliza a execução do programa.

## Estrutura do Projeto

### Classe Estacionamento

#### Atributos
- `precoInicial`: Valor decimal cobrado para estacionar o veículo.
- `precoPorHora`: Valor decimal cobrado por hora de permanência.
- `veiculos`: Lista de strings que armazena as placas dos veículos estacionados.

#### Métodos
- `AdicionarVeiculo()`: Adiciona um veículo à lista de veículos estacionados.
- `RemoverVeiculo()`: Remove um veículo da lista e calcula o valor a ser pago.
- `ListarVeiculos()`: Lista todos os veículos estacionados.

### Programa Principal

O arquivo `Program.cs` contém o menu interativo que permite ao usuário interagir com o sistema. Ao iniciar, o programa solicita o preço inicial e o preço por hora, que serão utilizados para calcular o valor a ser pago quando um veículo for removido.

## Como Usar

1. Execute o programa.
2. Informe o preço inicial e o preço por hora quando solicitado.
3. Utilize o menu para realizar as operações desejadas:
   - Opção 1: Cadastrar um veículo
   - Opção 2: Remover um veículo
   - Opção 3: Listar veículos estacionados
   - Opção 4: Encerrar o programa
