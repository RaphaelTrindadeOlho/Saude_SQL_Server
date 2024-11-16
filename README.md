# Projeto Sistema de Saúde

Este projeto simula um sistema de gerenciamento de saúde utilizando SQL Server. Ele envolve a criação de tabelas para armazenar informações sobre pessoas, pacientes, médicos, medicamentos e receitas.

## Estrutura do Banco de Dados

O banco de dados `SISTEMASAUDE` possui as seguintes tabelas principais:

1. **PESSOA**: Contém informações gerais sobre as pessoas.
   - `PES_INT_ID` (ID da pessoa)
   - `PES_STR_NOME` (Nome da pessoa)
   - `PES_DATE_DATANASC` (Data de nascimento)
   - `PES_STR_SEXO` (Sexo)
   - `PES_STR_CPF` (CPF)

2. **PACIENTE**: Tabela que armazena informações específicas de pacientes.
   - `PAC_INT_ID` (ID do paciente)
   - `PAC_DATE_DATAREGISTRO` (Data de registro)
   - `PAC_STR_CONVENIO` (Convênio do paciente)
   - `PAC_STR_COMORBIDADE` (Comorbidade)
   - `PAC_STR_ALERGIA` (Alergia)

3. **DOUTOR**: Tabela com dados dos médicos.
   - `DOU_INT_ID` (ID do médico)
   - `DOU_STR_CRM` (CRM do médico)
   - `DOU_STR_ESPECIALIDADE` (Especialidade)
   - `DOU_STR_HOSPITAIS` (Hospitais associados)

4. **MEDICAMENTO**: Tabela contendo informações sobre os medicamentos.
   - `MED_INT_ID` (ID do medicamento)
   - `MED_STR_NOME` (Nome do medicamento)
   - `MED_STR_PRINCATIVO` (Princípio ativo)
   - `MED_DOU_DOSAGEM` (Dosagem)
   - `MED_DOU_PRECO` (Preço)
   - `MED_STR_FABRICANTE` (Fabricante)

5. **RECEITA**: Tabela para registrar receitas médicas.
   - `REC_INT_ID` (ID da receita)
   - `DOU_INT_ID` (ID do médico)
   - `PAC_INT_ID` (ID do paciente)
   - `REC_DATE_DATA` (Data da receita)

6. **RECEITA_MEDICAMENTO**: Tabela de junção que faz o relacionamento entre medicamentos e receitas.
   - `REC_INT_ID` (ID da receita)
   - `MED_INT_ID` (ID do medicamento)

## Relacionamentos entre as Tabelas

- **PESSOA e PACIENTE/DOUTOR**: Um relacionamento 1:1 foi criado para associar uma pessoa a um paciente e/ou a um doutor.
- **RECEITA e PACIENTE/DOUTOR**: Cada receita está associada a um paciente e a um doutor.
- **RECEITA e MEDICAMENTO**: Um relacionamento N:N entre as tabelas de receita e medicamento, permitindo que uma receita tenha múltiplos medicamentos e vice-versa.

## Scripts de Criação do Banco

O projeto contém os seguintes scripts:

1. Criação do banco de dados e tabelas.
2. Inserção de restrições de chave primária e chave estrangeira.
3. Definição de relacionamentos entre as tabelas.
4. Tabela de junção entre receitas e medicamentos.

## Como Usar

Para executar este projeto em seu ambiente SQL Server:

1. Abra o SQL Server Management Studio (SSMS).
2. Crie um novo banco de dados com o comando:
   ```sql
   CREATE DATABASE SISTEMASAUDE;
