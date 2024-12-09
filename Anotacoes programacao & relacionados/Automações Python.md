___
python -m venv nome_do_ambiente - comando para criar um ambiente virtual, para rodar o python quase como se fosse em uma VM
pip install pyinstaller - instalar para poder criar um executavel (.exe)
pyinstaller --onefile nome_do_seu_arquivo.py - compilar o código para .exe
o arquivo, que foi compilado, vai ser encontrado dentro de uma pasta chamada **dist**.

##### Código para gerar quantidade X de arquivo .txt

```python
import os

def criar_arquivos_txt(qtd_arquivos):
    caminho_pasta_CHAMADOS = os.path.expanduser("~\\\\Desktop\\\\CHAMADOS")
    
    # verifica se algum arquivo já existe
    arquivos_existentes = []
    for i in range(1, qtd_arquivos + 1):
        nome_arquivo = f"Coo{i}.txt"
        caminho_completo = os.path.join(caminho_pasta_CHAMADOS, nome_arquivo)
        
        if os.path.exists(caminho_completo):
            arquivos_existentes.append(nome_arquivo)
    
    # se algum arquivo existir, exibe quais e não cria nenhum
    if arquivos_existentes:
        print(f"Os seguintes arquivos já existem: {', '.join(arquivos_existentes)}. Nenhum arquivo será criado.")
    else:
        # se não houver arquivos existentes, cria os novos arquivos
        for i in range(1, qtd_arquivos + 1):
            nome_arquivo = f"Coo{i}.txt"
            caminho_completo = os.path.join(caminho_pasta_CHAMADOS, nome_arquivo)
            
            try:
                with open(caminho_completo, 'w') as f:
                    f.write(f"Este é o conteúdo do arquivo {i}.")
                print(f"Arquivo {nome_arquivo} criado com sucesso em: {caminho_pasta_CHAMADOS}.")
            except Exception as e:
                print(f"Erro ao criar o arquivo: {e}")

while True:
    try:
        quantidade = int(input("Quantos arquivos .txt deseja criar? "))
        if quantidade <= 0:
            print("Por favor, insira um número maior que zero.")
        else:
            break
    except ValueError:
        print("Entrada inválida! Por favor, insira um número inteiro, número de arquivos a criar.")
criar_arquivos_txt(quantidade)
```

```bash
Código .bat do script

@echo off
python C:\\Users\\01292385\\Documents\\automacoes\\criar-arquivo-Coo-txt.py
pause

```

___