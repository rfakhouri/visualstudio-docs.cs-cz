---
title: 'Návod: Vytvoření fragmentu kódu'
ms.date: 06/10/2019
ms.topic: conceptual
helpviewer_keywords:
- code snippets, creating
- code snippets, shortcut
- code snippets, template
- code snippets, replacements
- code snippets, references
- code snippets, imports
ms.assetid: 0dcaae11-39cf-4463-9c90-2494321251c2
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- VB
ms.workload:
- multiple
ms.openlocfilehash: 6f58581a601da59e7ff66a3bae5ddcb7432bf8e3
ms.sourcegitcommit: cc5fd59e5dc99181601b7db8b28d7f8a83a36bab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/11/2019
ms.locfileid: "66836104"
---
# <a name="walkthrough-create-a-code-snippet"></a>Návod: Vytvoření fragmentu kódu

Fragment kódu můžete vytvořit pouze v několika krocích. Všechno, co je třeba provést je vytvořit soubor XML, vyplnit odpovídající prvky a přidejte svůj kód do něj. Volitelně můžete provést pomocí nahrazení parametrů a odkazy na projekt. Importovat fragment kódu pro instalaci sady Visual Studio pomocí **Import** tlačítko **Správce fragmentů kódů** (**nástroje** > **kódu Správce fragmentů**).

## <a name="snippet-template"></a>Šablona fragmentu

Následující kód XML je šablona základního fragmentu:

```xml
<?xml version="1.0" encoding="utf-8"?>
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
    <CodeSnippet Format="1.0.0">
        <Header>
            <Title></Title>
        </Header>
        <Snippet>
            <Code Language="">
                <![CDATA[]]>
            </Code>
        </Snippet>
    </CodeSnippet>
</CodeSnippets>
```

## <a name="create-a-code-snippet"></a>Vytvoření fragmentu kódu

1. Vytvořte nový soubor XML v sadě Visual Studio a přidejte šablonu uvedenou výše.

2. Vyplňte název fragmentu kódu do **název** elementu. Použít název **druhou odmocninu**.

3. Vyplňte jazyk fragmentu kódu do **jazyk** atribut **kód** elementu. Pro C#, použijte **CSharp**a v jazyce Visual Basic použijte **VB**.

   > [!TIP]
   > Zobrazit všechny hodnoty dostupný jazyk, přejděte [kódu sekce atributy prvku](code-snippets-schema-reference.md#attributes) na [referenční dokumentace schématu fragmentů kódu](code-snippets-schema-reference.md) stránky.

4. Přidání fragmentu kódu v **CDATA** sekci **kód** elementu.

   Pro C#:

   ```xml
   <Code Language="CSharp">
       <![CDATA[double root = Math.Sqrt(16);]]>
   </Code>
   ```

   Nebo v jazyce Visual Basic:

   ```xml
   <Code Language="VB">
       <![CDATA[Dim root = Math.Sqrt(16)]]>
   </Code>
   ```

5. Uložte výstřižek jako *SquareRoot.snippet* (můžete ji uložit kamkoli).

## <a name="import-a-code-snippet"></a>Import kódu

1. Fragment kódu pro instalaci sady Visual Studio můžete importovat pomocí **Správce fragmentů kódů**. Otevřete výběrem **nástroje** > **Správce fragmentů kódů**.

2. Klikněte na tlačítko **Import** tlačítko.

3. Přejděte do umístění, kam jste uložili fragmentu kódu v předchozím postupu, vyberte ho a klikněte na tlačítko **otevřít**.

4. **Fragment kódu** otevře dialogové okno s výzvou, abyste se rozhodnete, jak přidat výstřižku z nabídky v pravém podokně. Jedna z možností by měla být **Moje fragmenty kódu**. Vyberte ho a klikněte na tlačítko **Dokončit**, pak **OK**.

5. Fragment je zkopírován do jednoho z následujících umístění, v závislosti na jazyk kódu:

   ::: moniker range="vs-2017"

   *%USERPROFILE%\Documents\Visual Studio 2017\Code Snippets\Visual C#\My Code Snippets*
    *%USERPROFILE%\Documents\Visual Studio 2017\Code Snippets\Visual Basic\My Code Snippets*

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   *%USERPROFILE%\Documents\Visual Studio 2019\Code Snippets\Visual C#\My Code Snippets*
    *%USERPROFILE%\Documents\Visual Studio 2019\Code Snippets\Visual Basic\My Code Snippets*

   ::: moniker-end

6. Otestujte fragment otevřením C# nebo projektu jazyka Visual Basic. Soubor kódu otevřen v editoru, zvolte **fragmenty** > **Vložit fragment** v místní nabídce pak **Moje fragmenty kódu**. Měli byste vidět fragment kódu s názvem **druhou odmocninu**. Poklepejte na něj.

   Fragment kódu je vložen do souboru kódu.

## <a name="description-and-shortcut-fields"></a>Pole Popis a zástupce

::: moniker range="vs-2017"

1. Popisná pole poskytují další informace o fragmentech kódů při zobrazení ve Správci fragmentů kódu. Zástupce je příznak, který mohou uživatelé zadat, aby vložili váš fragment. Upravte fragment kódu přidaný otevřením souboru *%USERPROFILE%\Documents\Visual Studio 2017\Code fragmenty\\[Visual C# nebo Visual Basic] \My Code Snippet\SquareRoot.snippet*.

::: moniker-end

::: moniker range=">=vs-2019"

1. Popisná pole poskytují další informace o fragmentech kódů při zobrazení ve Správci fragmentů kódu. Zástupce je příznak, který mohou uživatelé zadat, aby vložili váš fragment. Upravte fragment kódu přidaný otevřením souboru *%USERPROFILE%\Documents\Visual Studio 2019\Code fragmenty\\[Visual C# nebo Visual Basic] \My Code Snippet\SquareRoot.snippet*.

::: moniker-end

   > [!TIP]
   > Vzhledem k tomu, že při úpravě souboru v adresáři, kde ho umístili sady Visual Studio, nemusíte znovu importovat do sady Visual Studio.

2. Přidat **Autor** a **popis** prvků, které mají **záhlaví** prvek a vyplňte je.

3. **Záhlaví** prvek by měl vypadat přibližně takto:

   ```xml
   <Header>
       <Title>Square Root</Title>
       <Author>Myself</Author>
       <Description>Calculates the square root of 16.</Description>
   </Header>
   ```

4. Otevřít **Správce fragmentů kódů** a vyberte váš fragment kódu. V pravém podokně, Všimněte si, že **popis** a **Autor** pole jsou nyní zaplněna.

   ![Popis fragmentu kódu ve Správci fragmentů kódu](media/code-snippet-description-author.png)

5. Chcete-li přidat zástupce, přidejte **místní** element v rámci **záhlaví** element:

   ```xml
   <Header>
      <Title>Square Root</Title>
      <Author>Myself</Author>
      <Description>Calculates the square root of 16.</Description>
      <Shortcut>sqrt</Shortcut>
    </Header>
   ```

6. Uložte soubor výstřižku znovu.

7. Chcete-li otestovat zástupce, otevřete projekt, který jste použili, zadejte **sqrt** v editoru a stiskněte klávesu **kartu** (jednou v jazyce Visual Basic dvakrát C#).

   Fragment kódu vložen.

## <a name="replacement-parameters"></a>Nahrazující parametry

Můžete chtít fragmentu kódu nahradil uživatel. Například může být vhodné uživatele, nahraďte název proměnné v jejich aktuálního projektu. Můžete zadat dva druhy náhrad: literály a objekty. Použití [Literal element](code-snippets-schema-reference.md#literal-element) k identifikaci můžou nahradit aktuální soubor pro část kódu, který je zcela obsažen ve fragmentu kódu, ale pravděpodobně přizpůsobit po vložení kódu (například řetězec nebo číselná hodnota). Použití [prvek objektu](code-snippets-schema-reference.md#object-element) k identifikaci položky, která je potřeba ve fragmentu kódu, ale je pravděpodobně definována mimo samotný (například instance objektu nebo ovládací prvek) fragment kódu.

1. Povolit uživatelům snadno nahradit číslo, které chcete vypočítat druhou odmocninu, změnit **fragment** elementu *SquareRoot.snippet* to následujícím způsobem:

   ```xml
   <Snippet>
     <Code Language="CSharp">
       <![CDATA[double root = Math.Sqrt($Number$);]]>
     </Code>
     <Declarations>
       <Literal>
         <ID>Number</ID>
         <ToolTip>Choose the number you want the square root of.</ToolTip>
         <Default>16</Default>
       </Literal>
     </Declarations>
   </Snippet>
   ```

   Všimněte si, že náhradní literál je zadané ID (`Number`). Že ID je odkazován z fragmentu kódu podle okolní infrastrukturou s `$` znaků:

   ```xml
   <![CDATA[double root = Math.Sqrt($Number$);]]>
   ```

2. Uložte soubor výstřižku.

3. Otevřete projekt a Vložit fragment kódu.

   Vložení fragmentu kódu a upravovat literál je zvýrazněn pro nahrazení. Najeďte myší na parametr nahrazení zobrazíte popisek pro hodnotu.

   ![Popis parametru nahrazení fragmentu kódu v sadě Visual Studio Code](media/snippet-replacement-parameter-tooltip.png)

   > [!TIP]
   > Pokud existuje více než jeden parametr replacable v fragment kódu, můžete stisknout **kartu** přejděte od jednoho na druhý ke změně hodnot.

## <a name="import-a-namespace"></a>Importujte obor názvů

Fragment kódu slouží k přidání `using` – direktiva (C#) nebo `Imports` – příkaz (Visual Basic) včetně [Imports element](code-snippets-schema-reference.md#imports-element). Pro projekty .NET Framework, můžete také přidat odkaz na projekt s použitím [References – element](code-snippets-schema-reference.md#references-element).

Následující kód XML ukazuje fragment kódu, který používá metodu `File.Exists` v oboru názvů System.IO a proto se definuje **importy** – element pro import System.IO – obor názvů.

```xml
<?xml version="1.0" encoding="utf-8"?>
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
  <CodeSnippet Format="1.0.0">
    <Header>
      <Title>File Exists</Title>
      <Shortcut>exists</Shortcut>
    </Header>
    <Snippet>
      <Code Language="CSharp">
        <![CDATA[var exists = File.Exists("C:\\Temp\\Notes.txt");]]>
      </Code>
      <Imports>
        <Import>
          <Namespace>System.IO</Namespace>
        </Import>
      </Imports>
    </Snippet>
  </CodeSnippet>
</CodeSnippets>
```

## <a name="see-also"></a>Viz také:

- [Referenční informace ke schématu fragmentů kódu](../ide/code-snippets-schema-reference.md)