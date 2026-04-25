# 🕒 Sistema de Controle de Horas
Sistema web desenvolvido em Python (Flask) para gerenciamento de horas trabalhadas por colaboradores, com controle de acesso, relatórios avançados e importação de dados.

## Visão Geral
O sistema permite o controle completo de horas trabalhadas, com diferenciação de permissões entre usuários:

- Colaboradores: registram e acompanham suas próprias horas
- Administradores: possuem acesso total ao sistema

A aplicação foi projetada com foco em usabilidade, organização de dados e geração de relatórios, atendendo cenários corporativos.

## Funcionalidades

### Autenticação e Permissões
- Login seguro com controle de sessão
- Cadastro com validação de domínio empresarial (@geoprojetos.com.br)
- Controle de acesso por perfil (Administrador / Colaborador)
- Edição de perfil e senha

### Gestão de Colaboradores e Contratos
- Cadastro manual de colaboradores
- Importação em lote via Excel
- Cadastro e gerenciamento de contratos
- Suporte a IDs customizados (ex: COL001, GP9014)

### Registro de Horas
- Registro diário por data
- Registro mensal por contrato
- Interface com seleção de tipo de lançamento
- Controle automático de permissões (colaborador só registra para si)

### Consulta e Análise
- Visualização:
  - Detalhada (registros individuais)
  - Agregada (totais por colaborador/contrato/mês)
- Filtros avançados por:
  - Período
  - Colaborador
  - Contrato
- Ordenação dinâmica por colunas
- Totais automáticos exibidos

### Relatórios e Exportação
- Exportação para Excel em múltiplos formatos:
  - Padrão
  - Por colaborador
  - Por contrato
  - Relatório mensal (matriz)
- Relatórios personalizados com filtros

### Importação de Dados
__Colaboradores__
```
Coluna A: ID
Coluna B: Nome
```

__Contratos__
```
Coluna A: ID/GP
Coluna B: Nome
```
- Validação automática
- Tratamento de erros na importação

## Interface
- UI moderna e responsiva
- Navegação consistente
- Links de Perfil e Logout em todas as páginas
- Fluxo otimizado para cadastro e consulta

## Tecnologias Utilizadas
- Python 3
- Flask
- Pandas
- Openpyxl
- XlsxWriter
- HTML / CSS / JS

## Instalação e Execução
```bash
# Instalar dependências
pip install -r requirements.txt

# Executar aplicação
python src/main.py
```

Acesse no navegador:
```
http://localhost:5000
```

## Credenciais Padrão
```
Email: admin@geoprojetos.com.br
Senha: admin
```
Recomenda-se alterar a senha após o primeiro acesso.

## Acesso em Rede
Para acessar de outros dispositivos:
1. Descubra o IP da máquina:
```bash
ipconfig   # Windows
ifconfig   # Linux/Mac
```

2. Acesse via:
```
http://SEU_IP:5000
```

## Estrutura de Dados
O sistema utiliza um arquivo local (dados.json) para armazenamento:

- Colaboradores
- Contratos
- Registros de horas

Criado automaticamente na primeira execução.

## Estrutura do Projeto
```
src/
 ├── main.py
 ├── models/
 ├── routes/
 ├── templates/
 └── static/
     ├── css/
     └── js/
```

## Regras de Negócio
- Apenas emails corporativos são aceitos
- Colaboradores acessam apenas seus dados
- Administradores possuem controle total
- Senhas armazenadas com hash seguro

## Possibilidades de Expansão
O sistema foi estruturado de forma modular, permitindo fácil evolução para:
- Banco de dados relacional (PostgreSQL, etc.)
- API REST
- Autenticação externa (OAuth, SSO)
- Deploy em nuvem