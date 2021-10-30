---
title: Lista de comandos e flags
weight: 93
description: "Nesta seção, você vai encontrar uma lista com principais comandos do Ritchie."
---

---

## **Comandos**

### **Comandos de Configuração**

| Comandos      | Operação                                         |
| :------------ | :----------------------------------------------- |
| rit init      | inicia o Ritchie antes de usar                   |
| rit upgrade   | atualiza o Ritchie para a última versão estável  |
| rit tutorial  | habilita ou desabilita o tutorial                |
| rit -v        | retorna qual a versão atual instalada do Ritchie |

### **Comandos de Repositórios**

| Comandos              | Operação                                                                                         |
| :-------------------- | :----------------------------------------------------------------------------------------------- |
| rit add repo          | adiciona um novo repositório (para ter acesso as fórmulas desse repositório com Ritchie)         |
| rit list repo         | lista todos os repositórios disponíveis                                                          |
| rit update repo       | atualiza todos os repositórios (para acessar novas fórmulas desses repositórios com o Ritchie)   |
| rit set repo-priority | configura a prioridade do repositório                                                            |
| rit delete repo       | apaga um repositório (remove o acesso ao repositório de fórmulas com o Ritchie)                  |

### **Comandos de Fórmulas**


| Command                     | Operation                                                                               |
| :-------------------------- | :-------------------------------------------------------------------------------------- |
| rit create formula          | cria uma nova fórmula do zero (como também um novo repositório local, se necessário)    |
| rit build formula           | compila uma fórmula localmente para teste                                               |
| rit build formula --watch   | compila uma fórmula para teste, monitorando atualizações do código no tempo real        |
| rit rename formula          | renomeia uma fórmula local                                                              |
| rit list formula            | lista todas as fórmulas disponíveis em um/todos repositórios                            |

{{% alert color="danger" %}}

O comando rit build formula foi depreciado a partir da versão 2.5.0 do Ritchie.

{{% /alert %}}

### **Comandos de Autocomplete**

| Comandos                  | Operação                               |
| :------------------------ | :------------------------------------- |
| rit completion zsh        | adiciona o autocomplete via zsh        |
| rit completion bash       | adiciona o autocomplete via bash       |
| rit completion fish       | adiciona o autocomplete via fish       |
| rit completion powershell | adiciona o autocomplete via powershell |

### **Comandos de Ambiente**

| Comandos       | Operação                              |
| :------------- | :------------------------------------ |
| rit set env    | configura um novo ambiente            |
| rit show env   | mostra o atual ambiente que foi usado |
| rit delete env | apaga um ambiente                     |

### **Comandos de Credenciais**

| Comandos              | Operação                                        |
| :-------------------- | :---------------------------------------------- |
| rit set credential    | configura credenciais na sessão                 |
| rit list credential   | lista todas os nomes de credenciais e os campos |
| rit delete credential | permite apagar suas credenciais                 |

### **Comandos de Workspaces**

| Comandos             | Operações                                                                         |
| :------------------- | :-------------------------------------------------------------------------------- |
| rit list workspace   | lista todas as fórmulas do workspace                                              |
| rit add workspace    | adiciona um novo workspace                                                        |
| rit delete workspace | apaga um workspace                                                                |
| rit update workspace | atualiza um workspace (para acessar novas fórmulas desse workspace com o Ritchie) |

## **Flags**

### **Principais flags**

| Flags     | Operações                                                                              |
| :-------- | :------------------------------------------------------------------------------------- |
| -\-default | atribui os valores **default** configurados na fórmula                                |
| -\-docker  | executa a fórmula usando **Docker**                                                   |
| -\-help    | retorna a lista dos comandos executáveis que estão disponíveis e flags para o usuário |
| -\-local   | executa a fórmula **localmente**                                                      |
| -\-verbose | executa a fórmula sem detalhes dos logs                                               |
