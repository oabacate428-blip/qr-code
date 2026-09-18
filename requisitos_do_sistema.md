# Documento de Requisitos (requisitos.md)

Este documento descreve os requisitos funcionais, não funcionais, a especificação de casos de uso e as tecnologias para o **Gerador e Personalizador de QR Code**, estruturado a partir do Diagrama de Casos de Uso, das Narrativas e da arquitetura do sistema.

## 1. Visão Geral do Sistema

O sistema permite que o usuário crie e personalize QR Codes a partir de uma URL válida, customizando elementos visuais como cor, imagem central, tamanho e espessura, além de possibilitar o download ou compartilhamento do QR Code gerado.

## 2. Stack Tecnológico (Tecnologias Utilizadas)

* **Frontend:**
  * **HTML / CSS:** Estruturação e estilização das páginas.
  * **Bootstrap:** Framework CSS para criação de interface responsiva e componentes visuais.
  * **JavaScript:** Interatividade no lado do cliente (manipulação do DOM e atualizações dinâmicas).
* **Backend:**
  * **PHP:** Processamento das regras de negócio e gerenciamento de **sessões ativas**.
* **Banco de Dados:**
  * **SQL:** Persistência e gerenciamento de dados.
  * **PDO (PHP Data Objects):** Camada de abstração e acesso ao banco de dados garantindo segurança contra ataques como SQL Injection.

## 3. Requisitos Funcionais (RF)

| ID | Requisito Funcional | Descrição | 
 | ----- | ----- | ----- | 
| **RF01** | Inserir URL | O sistema deve permitir que o usuário insira uma URL legível/válida para a geração do QR Code. | 
| **RF02** | Selecionar Imagem Central | O sistema deve permitir o upload/seleção de uma imagem (Formatos: JPG ou PNG) para ser carregada no centro do QR Code. | 
| **RF03** | Selecionar Cor | O sistema deve permitir a escolha e personalização da cor do QR Code. | 
| **RF04** | Escolher Tamanho e Espessura | O sistema deve permitir ajustar o tamanho e a espessura das linhas/elementos do QR Code. | 
| **RF05** | Gerar QR Code | O sistema deve processar as configurações aplicadas e exibir o QR Code gerado. | 
| **RF06** | Baixar / Compartilhar QR Code | O sistema deve disponibilizar opções para download do arquivo final ou compartilhamento do QR Code gerado. | 

## 4. Requisitos Não Funcionais (RNF)

| ID | Requisito Não Funcional | Descrição | 
 | ----- | ----- | ----- | 
| **RNF01** | Compatibilidade de Formatos | Apenas formatos de imagem `.jpg` e `.png` devem ser aceitos para o logo central. | 
| **RNF02** | Validação de Entrada | A URL inserida precisa passar por uma pré-condição de validação para verificar se é legível/válida. | 
| **RNF03** | Usabilidade | A interface deve responder dinamicamente às personalizações de cor e posicionamento da imagem no centro do código. | 
| **RNF04** | Segurança no Banco de Dados | O acesso e persistência dos dados via SQL devem utilizar **PDO** com *prepared statements* para prevenir vulnerabilidades de SQL Injection. | 
| **RNF05** | Gerenciamento de Sessão | O backend em PHP deve manter **sessões ativas** e seguras para controle das requisições do usuário. | 

## 5. Especificação de Caso de Uso

### **UC01: Personalização e Geração de QR Code**

* **Identificador:** RF01 (e fluxos associados aos RF02, RF03, RF04, RF05, RF06)
* **Caso de Uso:** Inserir URL e Personalizar QR Code
* **Ator Principal:** Usuário
* **Pré-condição:** Inserir uma URL legível/válida no sistema.
* **Pós-condição:** O QR Code é gerado para a URL escolhida e fica disponível para download ou compartilhamento.

#### **Fluxo de Eventos (Narrativa de Execução)**

| Passo | Ação do Usuário | Resposta do Sistema | 
 | ----- | ----- | ----- | 
| **1** | Clicar no botão de criar/adicionar imagem. | — | 
| **2** | — | Abrir janela do sistema operacional para selecionar a imagem. | 
| **3** | Selecionar imagem nos formatos JPG ou PNG. | — | 
| **4** | — | Carregar e centralizar a imagem no centro do QR Code. | 
| **5** | Selecionar a cor desejada para o QR Code. | — | 
| **6** | — | Substituir a cor dos elementos do QR Code em tempo de exibição. | 
| **7** | Definir tamanho/espessura e clicar no botão para gerar o QR Code. | — | 
| **8** | — | Gerar o QR Code final e apresentar os botões para download e compartilhamento. | 
| **9** | Fazer o download do QR Code ou compartilhá-lo. | Concluir o processo. | 
