# SIFU - Módulo de Requerimentos e Turmas Especiais (UFERSA)

Este repositório contém o projeto de desenvolvimento do módulo de **Solicitação de Turma Especial e Requerimentos Acadêmicos** para o Sistema Integrado Funcional e Unificado (SIFU) da UFERSA.

---

## 1. Descrição do Problema
O processo de solicitação de turmas especiais e requerimentos gerais (quebra de pré-requisito, aproveitamento, etc.) na UFERSA apresenta fragmentação e falta de transparência. O problema central é a dependência de processos manuais e e-mails, o que gera atrasos nas análises das coordenações. 
Este projeto soluciona a centralização das solicitações, padronização documental e automação da triagem inicial.
*(Baseado no portfólio de processos: Gestão de Atividades Acadêmicas - UFERSA).*

### Perfis de Usuário
* **Discente:** Abre solicitações, anexa documentos (histórico/atestados) e acompanha o status.
* **Docente (Coordenador):** Analisa o mérito acadêmico e defere/indefere os pedidos.
* **Técnico-Administrativo:** Realiza a conferência documental e o registro final nos sistemas institucionais.
* **Externo:** Consulta a autenticidade de documentos emitidos.

### Informações Armazenadas
* **Dados do Solicitante:** Matrícula, curso, IRA e e-mail.
* **Dados do Requerimento:** Tipo de solicitação, disciplina alvo, justificativa textual e status.
* **Arquivos:** PDFs de histórico escolar e comprovantes.
* **Logs:** Histórico de movimentação do processo e decisões da coordenação.

---

## 2. Estimativa de Preço (AWS)
A infraestrutura foi planejada para operar dentro do **AWS Free Tier**, utilizando serviços Serverless para custo mínimo.

* **Custo Estimado Mensal:** ~$0.62 USD
* **URL da Estimativa:** [https://calculator.aws/#/estimate?id=660791d6512132773421edb54de7a2352d935ecc](https://calculator.aws/#/estimate?id=660791d6512132773421edb54de7a2352d935ecc)

---

## 3. Arquitetura do Sistema
O sistema utiliza uma arquitetura **Serverless** desacoplada:

1.  **Frontend:** Desenvolvido em **React.js** e hospedado no **AWS Amplify**.
2.  **API Gateway:** Gerencia as rotas e a comunicação segura.
3.  **Backend (Lambda):** Funções independentes para processar a lógica de negócio.
4.  **Banco de Dados (DynamoDB):** Armazenamento NoSQL para alta disponibilidade.
5.  **Storage (S3):** Armazenamento de arquivos e anexos dos discentes.

---

## 4. Identificação
* **Repositório:** `web-2026-1-KLEBSON`
* **Mantenedor:** KLEBSON DAVI DE SOUZA MAGALHAES
* **Usuário GitHub:** krepss

---

## 5. Implementação de IA Generativa
A IA Generativa (via Gemini API) será integrada como um **Agente de Triagem Acadêmica**:
* **Análise de Histórico (OCR + LLM):** Validação automática se o aluno possui os requisitos necessários para a turma especial ao subir o PDF.
* **Resumo de Justificativas:** Geração de pareceres resumidos para auxiliar a tomada de decisão do coordenador do curso.
