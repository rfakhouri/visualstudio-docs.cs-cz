---
title: "Anatomie programového testu UI | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: coded UI tests
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: c449c0e23fa3effa693059ed6d0b6c4a61b8470c
ms.sourcegitcommit: 69b898d8d825c1a2d04777abf6d03e03fefcd6da
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2018
---
# <a name="anatomy-of-a-coded-ui-test"></a>Anatomie programového uživatelského rozhraní testu

Když vytvoříte programového uživatelského rozhraní testovací v projektu programových testů uživatelského rozhraní, několik soubory budou přidány do vašeho řešení. V tomto tématu budeme používat příklad programový Test UI prozkoumat tyto soubory.  
  
 **Požadavky**  
  
-   Visual Studio Enterprise  
  
## <a name="contents-of-a-coded-ui-test"></a>Obsah programového testu UI  
 Když vytvoříte programového uživatelského rozhraní otestovat, **programového Tvůrce testování uživatelského rozhraní** vytvoří mapy uživatelského rozhraní v rámci testu a také metody test, parametry a kontrolní výrazy pro všechny testy. Také vytvoří soubor třídy pro každý test.  
  
|Soubor|Obsah|Upravitelné?|  
|----------|--------------|---------------|  
|[UIMap.Designer.cs](#UIMapDesignerFile)|[Část deklarace](#UIMapDesignerFile)<br /><br /> [Třída zdroje UIMap](#UIMapClass) (částečné, automaticky vygenerovaný)<br /><br /> [Metody](#UIMapMethods)<br /><br /> [Vlastnosti](#UIMapProperties)|Ne|  
|[UIMap.cs](#UIMapCS)|[Třída zdroje UIMap](#UIMapCS) (částečné)|Ano|  
|[CodedUITest1.cs](#CodedUITestCS)|[CodedUITest1 – třída](#CodedUITestCS)<br /><br /> [Metody](#CodedUITestMethods)<br /><br /> [Vlastnosti](#CodedUITestProperties)|Ano|  
|[UIMap.uitest](#UIMapuitest)|Mapa XML uživatelského rozhraní pro test.|Ne|  
  
###  <a name="UIMapDesignerFile"></a> UIMap.Designer.cs  
 Tento soubor obsahuje kód, který je automaticky vytvořené **programového Tvůrce testování uživatelského rozhraní** vytvoření testu. Tento soubor znovu vytvoří pokaždé, když se změní testu, tak, aby se nejedná o soubor, ve kterém můžete přidávat nebo upravovat kód.  
  
#### <a name="declarations-section"></a>Část deklarace  
 Tato část obsahuje následující deklarace pro uživatelské rozhraní Windows.  
  
```csharp  
using System;  
using System.CodeDom.Compiler;  
using System.Collections.Generic;  
using System.Drawing;  
using System.Text.RegularExpressions;  
using System.Windows.Input;  
using Microsoft.VisualStudio.TestTools.UITest.Extension;  
using Microsoft.VisualStudio.TestTools.UITesting;  
using Microsoft.VisualStudio.TestTools.UITesting.WinControls;  
using Microsoft.VisualStudio.TestTools.UnitTesting;  
using Keyboard = Microsoft.VisualStudio.TestTools.UITesting.Keyboard;  
using Mouse = Microsoft.VisualStudio.TestTools.UITesting.Mouse;  
using MouseButtons = System.Windows.Forms.MouseButtons;  
```  
  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.WinControls> Obor názvů je zahrnuté pro uživatelské rozhraní (UI) systému Windows. Pro webovou stránku uživatelského rozhraní, obor názvů by <xref:Microsoft.VisualStudio.TestTools.UITesting.HtmlControls>; pro uživatelské rozhraní Windows Presentation Foundation, obor názvů by být <xref:Microsoft.VisualStudio.TestTools.UITesting.WpfControls>.  
  
####  <a name="UIMapClass"></a>Třída zdroje UIMap  
 V další části souboru je <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> třídy.  
  
```csharp
[GeneratedCode("Coded UITest Builder", "10.0.21221.0")]  
public partial class UIMap  
```
  
Kód třídy začíná <xref:System.CodeDom.Compiler.GeneratedCodeAttribute> která je použita na třídu, která je deklarován jako konkrétní třídu. Si všimnete, že atribut platí také pro každé třídy v tomto souboru. Jiný soubor, který může obsahovat další kód pro tuto třídu je `UIMap.cs`, který je popsán později.  

Generovaný objekt `UIMap` třída obsahuje kód pro každou metodu, která byla určit, kdy byla zaznamenána test.  

```csharp
public void LaunchCalculator()  
public void AddItems()  
public void VerifyTotal()  
public void CleanUp()  
```

Tato část <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> třída také obsahuje generovaný kód pro každou vlastnost, který je požadován pro metody.

```csharp
public virtual LaunchCalculatorParams LaunchCalculatorParams  
public virtual AddItemsParams AddItemsParams  
public virtual VerifyTotalExpectedValues VerifyTotalExpectedValues  
public virtual CalculateItemsParams CalculateItemsParams  
public virtual VerifyMathAppTotalExpectedValues   
    VerifyMathAppTotalExpectedValues  
public UIStartMenuWindow UIStartMenuWindow  
public UIRunWindow UIRunWindow  
public UICalculatorWindow UICalculatorWindow  
public UIStartWindow UIStartWindow  
public UIMathApplicationWindow UIMathApplicationWindow  
```
  
#####  <a name="UIMapMethods"></a>Zdroje UIMap metody  
 Každá z metod má strukturu, která vypadá přibližně takto: `AddItems()` metoda. To je vysvětlené podrobněji pod kód, který se zobrazí spolu s přidat přehlednost zalomením řádku.

```csharp
/// <summary>  
/// AddItems - Use 'AddItemsParams' to pass parameters into this method.  
/// </summary>  
public void AddItems()  
{  
    #region Variable Declarations  
    WinControl uICalculatorDialog =   
        this.UICalculatorWindow.UICalculatorDialog;  
    WinEdit uIItemEdit =   
        this.UICalculatorWindow.UIItemWindow.UIItemEdit;  
    #endregion  
  
    // Type '{NumPad7}' in 'Calculator' Dialog  
    Keyboard.SendKeys(uICalculatorDialog,   
        this.AddItemsParams.UICalculatorDialogSendKeys,   
        ModifierKeys.None);  
  
    // Type '{Add}{NumPad2}{Enter}' in 'Unknown Name' text box  
    Keyboard.SendKeys(uIItemEdit,   
        this.AddItemsParams.UIItemEditSendKeys,   
        ModifierKeys.None);  
}
```

Souhrn komentář pro každou metodu definici informuje kterou třídu použít hodnoty parametrů pro danou metodu. V takovém případě je `AddItemsParams` třída, která je definována později v `UIMap.cs` souboru a která je také typ hodnoty, který je vrácen `AddItemsParams` vlastnost.  
  
 V horní části metody kódu je `Variable Declarations` oblast, která definuje místní proměnné pro uživatelské rozhraní objekty, které se budou používat metodou.  
  
 Tato metoda obě `UIItemWindow` a `UIItemEdit` jsou vlastnosti, které jsou přístupné pomocí `UICalculatorWindow` třída, která je definována později v `UIMap.cs` souboru.  
  
 Dále jsou řádky, které pomocí vlastnosti odesílat text z klávesnice aplikace Kalkulačka `AddItemsParams` objektu.  
  
 `VerifyTotal()` Metoda má velmi podobné strukturu a obsahuje následující kód kontrolní výraz.  

```csharp
// Verify that 'Unknown Name' text box's property 'Text' equals '9. '  
Assert.AreEqual(  
    this.VerifyTotalExpectedValues.UIItemEditText,   
    uIItemEdit.Text);  
```

 Název textového pole je uveden jako neznámá, protože na vývojáře aplikace Windows Kalkulačka neposkytl název veřejně dostupné pro ovládací prvek. <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A?displayProperty=fullName> Metoda selže, když se skutečnou hodnotou není rovno očekávaná hodnota, které by způsobily selhání testu. Všimněte si také, že obsahuje očekávaná hodnota desetinné čárky, který je následované mezerou. Pokud máte někdy a změnit tak funkce tento konkrétní test, musíte povolit pro tuto desetinné čárky a mezery.  
  
#####  <a name="UIMapProperties"></a>Vlastnosti zdroje UIMap  
 Kód pro každou vlastnost je také velmi standard v rámci třídy. Následující kód `AddItemsParams` vlastnost se používá v `AddItems()` metoda.  
  
```csharp
public virtual AddItemsParams AddItemsParams  
{  
    get  
    {  
        if ((this.mAddItemsParams == null))  
        {  
            this.mAddItemsParams = new AddItemsParams();  
        }  
        return this.mAddItemsParams;  
    }  
}
```

 Všimněte si, že vlastnost používá privátní místní proměnné s názvem `mAddItemsParams` pro uložení hodnotu, než se vrátí. Název vlastnosti a název třídy pro objekt, který vrátí jsou stejné. Je třída definovaná v později `UIMap.cs` souboru.  
  
 Každá třída, která je vrácena pomocí vlastnosti strukturovaná podobně. Tady je `AddItemsParams` třídy.  

```csharp
/// <summary>  
/// Parameters to be passed into 'AddItems'  
/// </summary>  
[GeneratedCode("Coded UITest Builder", "10.0.21221.0")]  
public class AddItemsParams  
{  
    #region Fields  
    /// <summary>  
    /// Type '{NumPad7}' in 'Calculator' Dialog  
    /// </summary>  
    public string UICalculatorDialogSendKeys = "{NumPad7}";  
  
    /// <summary>  
    /// Type '{Add}{NumPad2}{Enter}' in 'Unknown Name' text box  
    /// </summary>  
    public string UIItemEditSendKeys = "{Add}{NumPad2}{Enter}";  
    #endregion  
}
```

Stejně jako u všech tříd v `UIMap.cs` souboru začíná Tato třída <xref:System.CodeDom.Compiler.GeneratedCodeAttribute>. V této třídě malé je `Fields` oblast, která definuje řetězce, který chcete použít jako parametry pro <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard.SendKeys%2A?displayProperty=fullName> metoda, která se používá v `UIMap.AddItems()` metoda, která byla dříve popsané. Můžete napsat kód pro nahraďte hodnoty v těchto polí s řetězcem, než je volána metoda, ve kterém se používají tyto parametry.  

###  <a name="UIMapCS"></a> UIMap.cs  
 Ve výchozím nastavení tento soubor obsahuje částečné `UIMap` třída, která nemá žádné metody nebo vlastnosti.  
  
#### <a name="uimap-class"></a>Třída zdroje UIMap  
 Toto je, kde můžete vytvořit vlastní kód pro rozšíření funkcí <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> třídy. Kód, který vytvoříte v tomto souboru nebudou znovu generovat **programového Tvůrce testování uživatelského rozhraní** pokaždé, když se mění testu.  
  
 Žádná z částí <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> můžete použít metody a vlastnosti z jakékoliv jiné části <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> třídy.  
  
###  <a name="CodedUITestCS"></a>CodedUITest1.cs  
 Tento soubor je generován **programového Tvůrce testování uživatelského rozhraní**, ale nevytvoří znovu pokaždé, když test je změněn, takže můžete měnit kód v tomto souboru. Název souboru je vytvořen z název, který jste zadali pro test při jeho vytvoření.  
  
#### <a name="codeduitest1-class"></a>CodedUITest1 – třída

Ve výchozím nastavení tento soubor obsahuje definici jenom jedna třída.

```csharp
[CodedUITest]  
public class CodedUITest1  
```

<xref:Microsoft.VisualStudio.TestTools.UITesting.CodedUITestAttribute> Se automaticky použije na třídu, která umožňuje testování framework rozpoznat jako testování rozšíření. Všimněte si také, že se nejedná konkrétní třídu. Všechny třídy kódu je obsažený v tomto souboru.  
  
#####  <a name="CodedUITestProperties"></a>Vlastnosti CodedUITest1  
 Třída obsahuje dvě výchozí vlastnosti, které jsou umístěné v dolní části souboru. Nesmí být upraven.  
  
```csharp
/// <summary>  
/// Gets or sets the test context which provides  
/// information about and functionality for the current test run.  
///</summary>  
public TestContext TestContext  
public UIMap UIMap  
```
  
#####  <a name="CodedUITestMethods"></a>CodedUITest1 metody  
 Ve výchozím nastavení třída obsahuje pouze jednu metodu.  

```csharp
public void CodedUITestMethod1()  
```

 Tato metoda volá všechny `UIMap` metoda, která jste zadali, když jste si poznamenali svůj test, který je popsaný v části na [třída zdroje UIMap](#UIMapClass).  
  
 Oblasti, která je s názvem `Additional test attributes`, pokud uncommented, obsahuje dvě volitelné metody.  
  
```csharp
// Use TestInitialize to run code before running each test   
[TestInitialize()]  
public void MyTestInitialize()  
{  
    // To generate code for this test, select "Generate Code for Coded   
    // UI Test" from the shortcut menu and select one of the menu items.  
    // For more information on generated code, see   
    // http://go.microsoft.com/fwlink/?LinkId=179463  
  
    // You could move this line from the CodedUITestMethod1() method  
    this.UIMap.LaunchCalculator();  
}  
  
// Use TestCleanup to run code after each test has run  
[TestCleanup()]  
public void MyTestCleanup()  
{  
    // To generate code for this test, select "Generate Code for Coded   
    // UI Test" from the shortcut menu and select one of the menu items.  
    // For more information on generated code, see   
    // http://go.microsoft.com/fwlink/?LinkId=179463  
  
    // You could move this line from the CodedUITestMethod1() method  
    this.UIMap.CloseCalculator();  
}
```

 `MyTestInitialize()` Metoda má <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestInitializeAttribute> použít, který informuje rozhraní testování mohli volat tuto metodu než jiné metody testu. Podobně `MyTestCleanup()` metoda má <xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCleanupAttribute> použije na ni, která sděluje testování framework mohli volat tuto metodu za všechny ostatní metody testovací mít byla volána. Používání těchto metod je volitelný. Pro tento test `UIMap.LaunchCalculator()` metoda může být volána z `MyTestInitialize()` a `UIMap.CloseCalculator()` metoda může být volána z `MyTestCleanup()` místo z `CodedUITest1Method1()`.  
  
 Pokud přidáte další metody pro tuto třídu pomocí <xref:Microsoft.VisualStudio.TestTools.UITesting.CodedUITestAttribute>, zavolá rozhraní testování jednotlivých metod v rámci testu.  
  
###  <a name="UIMapuitest"></a> UIMap.uitest  
 Toto je soubor XML, představuje strukturu rozhraní programové otestovali zaznamenávání a všech jejích částí. Mezi ně patří třídy kromě metody a vlastnosti těchto tříd a akce. [UIMap.Designer.cs](#UIMapDesignerFile) soubor obsahuje kód, který je generován Tvůrce programového uživatelského rozhraní pro reprodukci strukturu testu a poskytuje připojení k rozhraní testování.  
  
 `UIMap.uitest` Soubor není přímo upravovat. Ale, můžete pomocí Tvůrce programového uživatelského rozhraní změnit test, který automaticky změní `UIMap.uitest` souboru a [UIMap.Designer.cs](#UIMapDesignerFile) souboru.  
  
## <a name="see-also"></a>Viz také

<xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap>   
<xref:Microsoft.VisualStudio.TestTools.UITesting.WinControls>   
<xref:Microsoft.VisualStudio.TestTools.UITesting.HtmlControls>   
<xref:Microsoft.VisualStudio.TestTools.UITesting.WpfControls>   
<xref:System.CodeDom.Compiler.GeneratedCodeAttribute>   
<xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A?displayProperty=fullName>   
<xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard.SendKeys%2A?displayProperty=fullName>   
<xref:Microsoft.VisualStudio.TestTools.UITesting.CodedUITestAttribute>   
<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestInitializeAttribute>   
<xref:Microsoft.VisualStudio.TestTools.UnitTesting.TestCleanupAttribute>   
[Použití automatizace uživatelského rozhraní k testování kódu](../test/use-ui-automation-to-test-your-code.md)   
[Vytváření programové testy uživatelského rozhraní](../test/use-ui-automation-to-test-your-code.md)   
[Osvědčené postupy pro programové testy uživatelského rozhraní](../test/best-practices-for-coded-ui-tests.md)   
[Testování rozsáhlé aplikace s více mapami uživatelského rozhraní](../test/testing-a-large-application-with-multiple-ui-maps.md)   
[Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)
