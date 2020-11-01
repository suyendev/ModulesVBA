![GitHub repo size](https://img.shields.io/github/repo-size/felipebacelo/ModulesVBA?style=for-the-badge)
![GitHub](https://img.shields.io/github/license/felipebacelo/ModulesVBA?style=for-the-badge)
![GitHub language count](https://img.shields.io/github/languages/count/felipebacelo/ModulesVBA?style=for-the-badge)
![GitHub All Releases](https://img.shields.io/github/downloads/felipebacelo/ModulesVBA/total?style=for-the-badge)
![GitHub followers](https://img.shields.io/github/followers/felipebacelo?style=for-the-badge)

# ModulesVBA

Módulos de Formatação e Preferências em VBA Excel.

### Desenvolvimento

Desenvolvido em Microsoft VBA Excel.
***
### Requisitos

* Habilitar Macros
* Habilitar Guia de Desenvolvedor

### Referências às Bibliotecas

* Visual Basic For Applications
* Microsoft Excel 16.0 Object Library
* OLE Automation
* Microsoft Office 16.0 Object Library
* Microsoft Forms 2.0 Object Library

### Compatibilidade

Estes módulos foram desenvolvidos no Excel 2019 (64 bits) e testados no Excel 2016 (64 bits). Sua compatibilidade é garantida para a versão 2016 e superiores. Sua utilização em versões anteriores pode ocasionar em não funcionamento do mesmo.

### Usabilidade

Para utilizar os módulos o usuário deverá:

* Realizar o download do arquivo ZIP: __ModulesVBA__.
* Abrir o Excel.
* Importar através do VBA os arquivos __ModControls.bas__ e __ModPreferences.bas__.
***

### Macros e Funções dos Módulos

#### ModControls

* FormatData (Macro utilizada para formatar datas)
* FormatMoeda (Macro utilizada para formatar moeda)
* FormatCEP (Macro utilizada para formatar CEP)
* FormatCPF (Macro utilizada para formatar CPF)
* FormatCNPJ (Macro utilizada para formatar CNPJ)
* FormatCelular (Macro utilizada para formatar celular)
* FormatTelefone (Macro utilizada para formatar telefone)
***

#### ModPreferences

* TelaMenu (Macro utilizada para desabilitar alguns recursos do Excel deixando-o com uma cara de executável)
* TelaNormal (Macro utilizada para retornar os recursos padrões de exibição do Excel)
* CriarPasta (Macro utilizada para criar pasta)
* SalvarPDF (Macro utilizada para salvar o arquivo em PDF)
* LimparPlanilha (Macro utilizada para limpar a planilha)
* SelecionaArquivo (Função utilizada para abrir a caixa de seleção de arquivos)
***

### Exemplo de Função Utilizada

```
Option Explicit

Function SelecionaArquivo(Optional Filtro As String = "", Optional Extensao As String = "", _
Optional Titulo As String = "", Optional Email As Boolean = False) As String
    
    Dim Caixa As FileDialog
    
    Set Caixa = Application.FileDialog(msoFileDialogOpen)
    
    With Caixa
        
        .InitialView = msoFileDialogViewDetails
        
        .InitialFileName = "C:\"
        
        .AllowMultiSelect = Email
        
        If Filtro <> Empty Then
            .Filters.Clear
            .Filters.Add Filtro, Extensao
        End If
        
    End With
    
    Caixa.Show
    
    SelecionaArquivo = ""
    
    On Error Resume Next
        SelecionaArquivo = Caixa.SelectedItems(1)
    
End Function
```

***
### Licenças

_MIT License_
_Copyright   ©   2020 Felipe Bacelo Rodrigues_

