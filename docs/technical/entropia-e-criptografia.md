# Entropia e Criptografia: Fundamentos Técnicos

## Resumo

Este documento explora os conceitos de entropia, criptografia e suas aplicações em sistemas de informação, com foco em assinaturas digitais e validação de autoria.

---

## 1. Entropia e Informação

### 1.1 Definição

A entropia, no contexto da teoria da informação, mede a imprevisibilidade ou aleatoriedade de um sistema. Em criptografia, a entropia é fundamental para a segurança de chaves e hashes.

### 1.2 Entropia como Assinatura

Quando dados pessoais (nome, CPF, data de nascimento) são transformados em hash, criam um vetor único que pode servir como assinatura criptográfica.

**Exemplo de conversão:**

```
Texto: Rafael Melo Reis|28742458870|27121980|São Paulo|ω
Hexadecimal (UTF-8): 52616661656c204d656c6f20526569737c323837343235383837307c32373132313938307c53c3836f205061756c6f7ccf89
```

---

## 2. Funções Hash

### 2.1 SHA-256

O SHA-256 (Secure Hash Algorithm 256-bit) é uma função criptográfica que produz um hash de 256 bits (64 caracteres hexadecimais).

**Características:**
- Determinístico (mesma entrada = mesmo hash)
- Resistente a colisões
- Irreversível (função unidirecional)
- Efeito avalanche (pequena mudança na entrada altera drasticamente o hash)

### 2.2 Aplicação em Autoria

Um hash pode servir como prova de autoria quando:
1. Contém dados do autor embutidos
2. É registrado em repositório público (GitHub, blockchain)
3. Possui timestamp verificável

**Hash Global de Exemplo:**
```
5f91a3c4b61fdcd2e10fbe1480f23e3f6e92624f1a1a44d8d7c3af21c9e6a8b7
```

---

## 3. Criptografia Simétrica vs Assimétrica

### 3.1 Criptografia Simétrica (AES)

- Usa a mesma chave para cifrar e decifrar
- Rápida e eficiente
- Exemplo: AES-256

### 3.2 Criptografia Assimétrica (RSA, ECC)

- Par de chaves: pública e privada
- Chave pública: distribui livremente
- Chave privada: mantida em sigilo
- Exemplo: RSA-2048, Elliptic Curve Cryptography

---

## 4. Cadeia de Custódia Digital

### 4.1 Princípios

1. **Integridade**: Verificável por hash
2. **Rastreabilidade**: Histórico completo de mudanças
3. **Autenticidade**: Assinatura digital verificável
4. **Temporalidade**: Timestamp confiável

### 4.2 Implementação no Git

O Git utiliza SHA-1 (e SHA-256 em versões recentes) para:
- Identificar commits
- Verificar integridade de arquivos
- Criar histórico imutável

---

## 5. Conversão Hexadecimal

### 5.1 Tabela de Conversão ASCII → Hex

| Caractere | Hexadecimal | Caractere | Hexadecimal |
|-----------|-------------|-----------|-------------|
| R | 52 | a | 61 |
| f | 66 | e | 65 |
| l | 6c | (espaço) | 20 |
| M | 4d | o | 6f |

### 5.2 Aplicação Prática

Dados pessoais podem ser embutidos em:
- Chaves criptográficas
- Hashes de documentos
- Metadados de arquivos
- Commits de repositórios

---

## 6. Segurança e Boas Práticas

### 6.1 Proteção de Dados Pessoais

⚠️ **ATENÇÃO**: Nunca incluir dados sensíveis (CPF, senhas) em:
- Código fonte público
- Commits de git
- Arquivos de configuração versionados

### 6.2 Uso Adequado de Hashes

✅ **Boas práticas:**
- Usar salt único para cada hash
- Empregar funções modernas (SHA-256, SHA-3, BLAKE2)
- Manter registro de timestamps
- Utilizar repositórios públicos para prova de autoria

---

## 7. Spintronics e Computação Quântica

### 7.1 Spin Eletrônico

O spin eletrônico representa um estado quântico que pode ser usado para armazenar informação:
- **Spin Up (↑)**: Estado +1/2
- **Spin Down (↓)**: Estado -1/2

### 7.2 Válvula de Spin

Tecnologia que controla o fluxo de elétrons baseado no spin, reduzindo o consumo de energia:
- **Alinhado**: Resistência baixa (corrente flui)
- **Desalinhado**: Resistência alta (corrente bloqueada)

### 7.3 Aplicações

- Memórias MRAM (Magnetoresistive RAM)
- Armazenamento de alta densidade
- Computação de baixo consumo energético

---

## 8. Conclusão

A entropia e a criptografia formam a base da segurança digital moderna. O uso correto desses conceitos permite:

1. **Autoria verificável** através de hashes e assinaturas digitais
2. **Integridade de dados** via funções hash criptográficas
3. **Confidencialidade** por meio de criptografia adequada
4. **Rastreabilidade** usando sistemas de controle de versão

---

## Referências

1. SCHNEIER, Bruce. **Applied Cryptography**. John Wiley & Sons, 2015.
2. SHANNON, Claude E. **A Mathematical Theory of Communication**. Bell System Technical Journal, 1948.
3. MENEZES, Alfred J.; VAN OORSCHOT, Paul C.; VANSTONE, Scott A. **Handbook of Applied Cryptography**. CRC Press, 1996.
4. National Institute of Standards and Technology (NIST). **FIPS 180-4: Secure Hash Standard (SHS)**, 2015.
