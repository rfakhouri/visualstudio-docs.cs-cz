---
title: 'Návod: Ladění textové šablony přistupující k modelu'
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.technology: vs-ide-modeling
ms.openlocfilehash: afa61e3d6158e5651fdc88969270a3bcf3af63c5
ms.sourcegitcommit: 4c0bc21d2ce2d8e6c9d3b149a7d95f0b4d5b3f85
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/20/2018
---
# <a name="walkthrough-debugging-a-text-template-that-accesses-a-model"></a>Návod: Ladění textové šablony přistupující k modelu
Když změníte nebo přidáte textové šablony v řešení jazyka domény, může docházet k chybám při modul transformuje šablony ke zdrojovému kódu nebo při kompilaci generovaného kódu. Následující návod ukazuje některé z akcí, které můžete provést k ladění textové šablony.

> [!NOTE]
>  Další informace o text šablony obecně platí, viz [generování kódu a textové šablony T4](../modeling/code-generation-and-t4-text-templates.md). Další informace o ladění textové šablony najdete v tématu [návod: ladění textové šablony](http://msdn.microsoft.com/Library/5c3fd3b7-c110-4e86-a22f-d5756be6b94f).

## <a name="creating-a-domain-specific-language-solution"></a>Vytváření řešení jazyka domény
 V tomto postupu vytvoříte jazyka domény řešení, které má následující vlastnosti:

-   Název: DebuggingTestLanguage

-   Šablona řešení: minimální jazyk

-   Příponu souboru: .ddd

-   Název společnosti: Fabrikam

 Další informace o vytváření řešení jazyka domény najdete v tématu [postupy: vytvoření řešení jazyk specifické pro doménu](../modeling/how-to-create-a-domain-specific-language-solution.md).

## <a name="creating-a-text-template"></a>Vytváření textové šablony
 Přidáte šablonu text do vašeho řešení.

#### <a name="to-create-a-text-template"></a>Chcete-li vytvořit textové šablony

1.  Sestavte řešení a spustit ji v ladicím programu. (Na **sestavení** nabídky, klikněte na tlačítko **znovu sestavit řešení**a pak na **ladění** nabídky, klikněte na tlačítko **spustit ladění**.) Novou instanci sady Visual Studio otevře ladění projektu.

2.  Přidejte textový soubor s názvem `DebugTest.tt` k ladění projektu.

3.  Ujistěte se, že **Custom Tool** vlastnost DebugTest.tt je nastavena na `TextTemplatingFileGenerator`.

## <a name="debugging-directives-that-access-a-model-from-a-text-template"></a>Ladění direktivy, které přístup k modelu z textové šablony
 Než se dostanete k modelu z příkazy a výrazy v textové šablony, nejprve je třeba volat generovaného procesoru direktiv. Volání metody generované procesoru direktiv zpřístupní třídy v modelu kód šablony text jako vlastnosti. Další informace najdete v tématu [přístup k modely z textové šablony](../modeling/accessing-models-from-text-templates.md).

 V následujících postupech se ladění nesprávným názvem direktivy a s názvem nesprávný vlastnost.

#### <a name="to-debug-an-incorrect-directive-name"></a>Chcete-li ladit nesprávným názvem direktivy

1.  Nahraďte kód v DebugTest.tt následujícím kódem:

    > [!NOTE]
    >  Kód obsahuje chybu. Chyba se sektory za účelem ladění.

    ```csharp
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ modelRoot processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>

    Model: <#= this.ExampleModel #>
    <#
    foreach (ExampleElement element in this.ExampleModel.Elements)
    {
    #>
        Element: <#= element.Name #>
    <#
    }
    #>
    ```

    ```vb
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ modelRoot processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>

    Model: <#= Me.ExampleModel #>
    <#
    For Each element as ExampleElement in Me.ExampleModel.Elements
    #>
        Element: <#= element.Name #>
    <#
    Next
    #>
    ```

2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na DebugTest.tt a pak klikněte na tlačítko **spustit nástroj pro vlastní**.

     **Seznam chyb** okně se zobrazí tato chyba:

     **Procesor s názvem 'DebuggingTestLanguageDirectiveProcessor' nepodporuje direktiva s názvem 'modelRoot'. Transformace se nespustí.**

     V takovém případě direktivy volání obsahuje nesprávný název direktivy. Zadali jste `modelRoot` jako název direktivy, ale správný název direktivy je `DebuggingTestLanguage`.

3.  Dvakrát klikněte na chybu v **seznam chyb** okno Přejít ke kódu.

4.  Chcete-li kód, změňte direktivu název `DebuggingTestLanguage`.

     Změna je označený.

    ```csharp
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>
    ```

    ```vb
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>
    ```

5.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na DebugTest.tt a pak klikněte na tlačítko **spustit nástroj pro vlastní**.

     Systém teď transformuje textové šablony a vygeneruje odpovídající výstupní soubor. Neuvidíte všechny chyby **seznam chyb** okno.

#### <a name="to-debug-an-incorrect-property-name"></a>Chcete-li ladit s názvem nesprávný vlastnost

1.  Nahraďte kód v DebugTest.tt následujícím kódem:

    > [!NOTE]
    >  Kód obsahuje chybu. Chyba se sektory za účelem ladění.

    ```csharp
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>

    Model: <#= this.ExampleModel #>
    <#
    foreach (ExampleElement element in this.ExampleModel.Elements)
    {
    #>
        Element: <#= element.Name #>
    <#
    }
    #>
    ```

    ```vb
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>

    Model: <#= Me.ExampleModel #>
    <#
    For Each element as ExampleElement in Me.ExampleModel.Elements
    #>
        Element: <#= element.Name #>
    <#
    Next
    #>
    ```

2.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na DebugTest.tt a pak klikněte na tlačítko **spustit nástroj pro vlastní**.

     **Seznam chyb** okno se zobrazí a zobrazí jedno z těchto chyb:

     (C#)

     **Kompilování transformace: Microsoft.VisualStudio.TextTemplating\<GUID >. GeneratedTextTransformation' pro 'ExampleModel' neobsahuje definici**

     (Visual Basic)

     **Kompilování transformace: 'ExampleModel' není členem ' Microsoft.VisualStudio.TextTemplating\<GUID >. GeneratedTextTransformation'.**

     V takovém případě obsahuje kód text šablony s názvem nesprávný vlastnost. Zadali jste `ExampleModel` jako název vlastnosti, ale vlastnost správný název je `LibraryModel`. Můžete najít název správné vlastnosti v obsahuje parametr, jak je vidět v následujícím kódu:

    ```
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>
    ```

3.  Dvakrát klikněte na chybu v okně Seznam chyb přejít ke kódu.

4.  Chcete-li kód, změňte název vlastnosti do `LibraryModel` v kódu text šablony.

     Změny se zvýrazněnou.

    ```csharp
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>

    Model: <#= this.LibraryModel #>
    <#
    foreach (ExampleElement element in this.LibraryModel.Elements)
    {
    #>
        Element: <#= element.Name #>
    <#
    }
    #>
    ```

    ```vb
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>
    <#@ output extension=".txt" #>
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>

    Model: <#= Me.LibraryModel #>
    <#
    For Each element as ExampleElement in Me.LibraryModel.Elements
    #>
        Element: <#= element.Name #>
    <#
    Next
    #>
    ```

5.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na DebugTest.tt a pak klikněte na tlačítko **spustit nástroj pro vlastní**.

     Systém teď transformuje textové šablony a vygeneruje odpovídající výstupní soubor. Neuvidíte všechny chyby **seznam chyb** okno.