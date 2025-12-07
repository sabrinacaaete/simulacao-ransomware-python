# 🔒 Simulação de Ransomware: Estudo de Criptografia Simétrica em Python

> ⚠️ **DISCLAIMER:** Este projeto foi desenvolvido estritamente para fins educacionais em ambiente controlado, a partir do bootcamp de cibersegurança oferecido pela DIO. O objetivo é compreender o funcionamento de malwares para desenvolver melhores estratégias de defesa (Blue Team). Não utilize este código em máquinas sem autorização.

## 🎯 Objetivo do Projeto
Demonstrar na prática como opera a lógica de um Ransomware básico, focando na **tríade de Disponibilidade** da Segurança da Informação. O script realiza a varredura de diretórios e aplica criptografia simétrica nos arquivos, tornando-os inacessíveis sem a chave correta.

## 🛠️ Tecnologias e Conceitos
* **Linguagem:** Python 3
* **Biblioteca:** `cryptography.fernet` (Implementação de criptografia simétrica baseada em AES).
* **Conceitos:**
    * Manipulação de Arquivos (File I/O).
    * Recursividade em diretórios (`os.walk`).
    * Gerenciamento de Chaves Criptográficas.

## ⚙️ Como Funciona (Análise Técnica)

### 1. O Agente de Criptografia (`ransomware.py`)
O script atua simulando a "carga útil" (payload) do malware:
1.  **Geração de Chave:** Cria uma chave simétrica única.
2.  **Varredura (Discovery):** Percorre todas as subpastas a partir do diretório alvo.
3.  **Encriptação:** Lê o conteúdo original do arquivo, encripta em memória e sobscreve o arquivo original.
4.  **Nota de Resgate:** Cria um arquivo de texto informando o ataque (simulação).

### 2. O Agente de Recuperação (`descriptografar.py`)
Simula a ferramenta que seria entregue após o "pagamento do resgate":
1.  Lê a chave gerada anteriormente.
2.  Reverte o processo matemático, devolvendo a integridade original dos arquivos.

## 🛡️ Perspectiva de Defesa (Blue Team)
Como detectar ou prevenir este tipo de comportamento?
* **Monitoramento de I/O:** Alertas sobre processos que tentam modificar muitos arquivos em curto período de tempo.
* **Honeypots:** Criação de arquivos falsos na rede para servirem de "isca". Se forem tocados, o alerta é disparado.
* **Backups:** A única garantia real contra Ransomware é ter backups offline e imutáveis.

---
*Desenvolvido por Sabrina Caaetê como parte do portfólio de estudos em Cibersegurança.*
