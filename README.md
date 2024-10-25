# Descrição do Script
Este script em Python lê todos os arquivos no formato ```.s2p``` de uma pasta especificada, extrai os parâmetros S 
(como ```S11```, ```S21```, ```S12```, ```S22```) e armazena os dados em um arquivo Excel com duas abas diferentes:

- **Aba 1: Valores Magnitude e Fase:** Contém as colunas de frequência, parte real e parte imaginária dos parâmetros S escolhidos para cada arquivo ```.s2p```.
- **Aba 2: Valores em dB:** Contém as colunas de frequência e o módulo do parâmetro S escolhido, 
convertido em decibéis (```10×log(𝑆real)```).

### Funcionalidades:
1. **Leitura de Arquivos** ```.s2p```: O script lê arquivos ```.s2p```, que são comumente usados para armazenar parâmetros S 
de dispositivos de duas portas (como ```S11```, ```S21```, ```S12```, ```S22```).
2. **Extração de Parâmetros S**: Para cada arquivo, o usuário pode escolher qual parâmetro S será extraído 
(por exemplo, ```S11```, ```S21```, ```S12```, ```S22```).
3. **Cálculo de Módulo em dB:** Além de extrair os valores magnitude e fase dos parâmetros S, o script também calcula o módulo desses valores em decibéis (dB).
4. **Salvamento em Planilha Excel:** Os dados extraídos são organizados em duas abas de uma planilha Excel:
    - **Aba "Valores Magnitude e Fase":** Contém a frequência, as partes real e imaginária dos parâmetros S para cada arquivo.
    - **Aba "Valores em dB":** Contém a frequência e o módulo em decibéis do parâmetro S escolhido.

### Estrutura do Código:

**Função** ```ler_s2p```: Lê o conteúdo dos arquivos ```.s2p```, extraindo a frequência e os valores de magnitude e fase dos parâmetros S.

**Função** ```calcular_modulo_s_db```: Calcula o módulo do parâmetro S escolhido em dB, garantindo que valores menores ou iguais a zero sejam tratados adequadamente.

**Função** ```salvar_para_excel```: Faz a leitura de todos os arquivos ```.s2p``` de uma pasta e salva os resultados em uma planilha Excel com duas abas.


### Como Usar:
1. Coloque seus arquivos ```.s2p``` em uma pasta específica.
2. Edite os seguintes parâmetros no script:
    - **caminho_pasta:** O caminho para a pasta onde estão os arquivos ```.s2p```.
    - **nome_excel:** O nome do arquivo Excel que será gerado.
    - **s_param:** O parâmetro S que você deseja analisar (ex.: ```S11```, ```S21```, ```S12```, ou ```S22```).
3. Execute o script, que irá ler todos os arquivos da pasta e gerar um arquivo Excel com os resultados organizados.

### Exemplo:
```
caminho_pasta = 'caminho/para/sua/pasta'
nome_excel = 'resultados_s2p.xlsx'
s_param = 'S11'  # Escolha entre S11, S21, S12, ou S22
salvar_para_excel(caminho_pasta, nome_excel, s_param)
```

O arquivo ```resultados_s2p.xlsx``` será gerado contendo as abas "Valores Magnitude e Fase" e "Valores em dB", com os dados correspondentes a cada arquivo ```.s2p```.

### Dependências:

- ```pandas```: para manipulação de DataFrames e salvar o arquivo Excel.
Você pode instalar o ```pandas``` com:

```
pip install pandas
```