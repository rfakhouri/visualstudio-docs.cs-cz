---
title: "Použití automatizace uživatelského rozhraní k testování kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.codedUITest
- vs.codedUITest.recorder
- vs.codedUITest.testbuilder
- vs.codedUITest.addAssertions
- vs.codedUITest.createdialog
helpviewer_keywords:
- automated tests, testing UI interface
- coded UI test
ms.author: gewarren
manager: ghogen
ms.workload: multiple
author: gewarren
ms.openlocfilehash: fafb9bc38aca51db6baf6cace6dc887db60ed8c8
ms.sourcegitcommit: 7ae502c5767a34dc35e760ff02032f4902c7c02b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/09/2018
---
# <a name="use-ui-automation-to-test-your-code"></a>Použití automatizace uživatelského rozhraní k testování kódu

Automatizované testy, které jednotky vaší aplikace pomocí jeho uživatelské rozhraní (UI) se označují jako *programové testy uživatelského rozhraní* (CUITs). Tyto testy zahrnují funkční testování ovládacích prvků uživatelského rozhraní. Které vám umožní ověřte, zda je správně funguje celou aplikaci, včetně jeho uživatelské rozhraní. Programové testy uživatelského rozhraní jsou obzvláště užitečná, kterých je ověření nebo jiné logiku v uživatelském rozhraní, například v na webové stránce. Používají se také často k automatizaci existující manuálního testu.  

Jak je znázorněno na následujícím obrázku, možné typické vývojového prostředí, kde na začátku jednoduše sestavit aplikaci (F5) a klikněte na tlačítko prostřednictvím ovládacích prvků uživatelského rozhraní pro ověřte, zda jsou správně funguje věcí. Můžete pak rozhodnout vytvořit programového testu, takže nemusíte pokračovat k testování aplikace ručně. V závislosti na konkrétní funkce testuje ve vaší aplikaci můžete napsat kód pro testu funkční, nebo pro test integrace, který může nebo nemusí zahrnovat testování na úrovni uživatelského rozhraní. Pokud chcete jednoduše přímý přístup k některé obchodní logiky, může kód testování částí. Ale za určitých okolností může být výhodné zahrnují testování různých ovládacích prvků uživatelského rozhraní v aplikaci. Programového testu uživatelského rozhraní můžete automatizovat počáteční scénář (F5), ověření, že tento změn kódu nemá negativní vliv na funkci aplikace.  

![Testování během vývoje aplikace](../test/media/cuit_overview.png "CUIT_Overview")  

Vytvoření programového testu uživatelského rozhraní je snadné. Můžete jednoduše provést test ručně při testování Tvůrce CUIT běží na pozadí. Můžete také určit, co by zobrazit hodnoty v konkrétních polí. Tvůrce testu CUIT zaznamenává vaše akce a generuje kód z nich. Po vytvoření testu ho můžete upravit v specializované editor, který umožňuje měnit posloupnost akcí.

Specializované Tvůrce testu CUIT a editor snadno vytvářet a upravovat programové testy uživatelského rozhraní, i když jsou svoje dovednosti hlavní soustředěné ve testování místo kódování. Ale pokud vývojáři a chcete rozšířit test pokročilejší způsobem, kód strukturovaná, aby bylo jasné pro kopírování a adaptaci. Může například záznam testu něco na webu a upravte generovaný kód pro přidání smyčku nakoupí mnoho položek.  

**Požadavky**

- Visual Studio Enterprise

Další informace o tom, které jsou podporovány platformy a konfigurace pomocí programových testů uživatelského rozhraní najdete v tématu [podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md).  

**V tomto tématu**
  
-   [Vytváření programové testy uživatelského rozhraní](#VerifyingCodeUsingCUITCreate)  
  
    -   [Main – procedura](#VerifyingCodeUsingCUITCreate)  
  
    -   [Spuštění a zastavení aplikace](#starting)  
  
    -   [Ověření vlastnosti ovládacích prvků uživatelského rozhraní](#VerifyingCodeUsingCUITGenerateAssertions)  
  
-   [Přizpůsobení vaší programového testu uživatelského rozhraní](#VerifyingCodeCUITModify)  
  
    -   [Generovaný kód](#generatedCode)  
  
    -   [Kódování uživatelského rozhraní řízení akcí a vlastností](#actions)  
  
    -   [Ladění](#debugging)  
  
-   [Co je další](#VerifyCodeUsingCUITWhatsNext)  
  
##  <a name="VerifyingCodeUsingCUITCreate"></a>Vytváření programové testy uživatelského rozhraní  
  
1.  **Vytvoření projektu programového testu uživatelského rozhraní.**  
  
     Programové testy uživatelského rozhraní musí být obsažené v projektu programových testů uživatelského rozhraní. Pokud ještě nemáte projekt programového testu uživatelského rozhraní, vytvořte. V **Průzkumníku řešení**, v místní nabídce řešení, zvolte **přidat**, **nový projekt** a pak vyberte buď **jazyka Visual Basic** nebo **Visual C#**. V dalším kroku vyberte **Test**, **programového testu uživatelského rozhraní**.  
  
    -   *Se nezobrazí **programového testu uživatelského rozhraní** šablony projektu.*  
  
         Používáte verzi Visual Studia, která nepodporuje programové testy uživatelského rozhraní. Pokud chcete vytvořit programové testy uživatelského rozhraní, musíte použít Visual Studio Enterprise.  
  
2.  **Přidejte soubor programových testů uživatelského rozhraní.**  
  
     Pokud jste právě vytvořili projekt programového uživatelského rozhraní, je automaticky přidá první soubor CUIT. Pokud chcete přidat jiný testovací soubor, otevřete v místní nabídce na projekt programových testů uživatelského rozhraní, přejděte na **přidat**a potom zvolte **programových testů uživatelského rozhraní**.  
  
     ![Vytvoření programového testu UI](../test/media/codedui_create.png "CodedUI_Create")  
  
     V **generovat kód pro programového testu uživatelského rozhraní** dialogovém okně vyberte **záznam akcí, upravte mapování uživatelského rozhraní nebo přidání kontrolních výrazů**.  
  
     ![Vyberte zaznamenávat akce](../test/media/codedui_codegendialogb.png "CodedUI_CodeGenDialogB")  
  
     Zobrazí se Tvůrce programového testu uživatelského rozhraní a je minimalizován Visual Studio.  
  
     ![Programový Tvůrce testu uživatelského rozhraní](../test/media/codedui_testbuilder.png "CodedUI_TestBuilder")  
  
3.  **Zaznamenejte sekvenci akcí**.  
  
     **Chcete-li spustit záznam**, vyberte **záznam** ikonu. Provedení akce, které chcete testovat ve vaší aplikaci, včetně spouštění aplikace v případě potřeby.  
  
     Například pokud testujete webovou aplikaci, můžete spustit prohlížeč, přejděte na web a přihlaste se k aplikaci.  
  
     **K pozastavení záznamu**, například pokud máte jak nakládat s příchozí pošty, zvolte **pozastavit**.  
  
    > [!WARNING]
    >  Všechny akce prováděné na ploše, bude zaznamenán. Pozastavení záznamu při provedení akce, které může vést k citlivá data nebudou zahrnuty do záznamu.  
  
     **Chcete-li odstranit akce** , které jste si poznamenali omylem, zvolte **upravit akce**.  
  
     **Generování kódu** , bude replikovat vaše akce, vyberte **generovat kód** ikonu a zadejte název a popis pro programové uživatelské rozhraní test – metoda.  
  
4.  **Ověřte hodnoty v polích uživatelského rozhraní, jako je například textová pole**.  
  
     Zvolte **přidat kontrolní výrazy** v programového Tvůrce testu uživatelského rozhraní a potom vyberte kontrolní mechanismus uživatelského rozhraní v běžící aplikaci. V seznamu vlastností, který se zobrazí, vyberte vlastnosti, například **Text** v textovém poli. V místní nabídce vyberte **přidat kontrolní**. V dialogovém okně vyberte relační operátor porovnání hodnota a chybová zpráva.  
  
     Zavřete okno kontrolní výraz a zvolte **generovat kód**.  
  
     ![Cílení na element programového testu UI](../test/media/codedui_1.png "CodedUI_1")  
  
    > [!TIP]
    >  Alternativní mezi zaznamenávání akcí a ověření hodnoty. Generovat kód na konci každé pořadí akcí nebo ověření. Pokud chcete, bude možné později vložit nových akcí a ověření.  
  
     Další podrobnosti najdete v tématu [ověřování vlastnosti ovládacích prvků](#VerifyingCodeUsingCUITGenerateAssertions).  
  
5.  **Zobrazení kódu generovaného testovací**.  
  
     Chcete-li zobrazit generovaného kódu, zavřete okno Tvůrce testu uživatelského rozhraní. V kódu se zobrazí názvy, které jste zadali pro každý krok. Kód je v souboru CUIT, kterou jste vytvořili:  
  
    ```csharp  
    [CodedUITest]  
    public class CodedUITest1  
    { ...  
      [TestMethod]  
      public void CodedUITestMethod1()  
      {  
          this.UIMap.AddTwoNumbers();  
          this.UIMap.VerifyResultValue();  
          // To generate more code for this test, select   
          // "Generate Code" from the shortcut menu.  
      }  
    }  
    ```  
  
6.  **Přidat další akce a kontrolní výrazy**.  
  
     Umístěte kurzor v odpovídajícím bodě v metodě testu a pak v místní nabídce zvolte **generovat kód pro programové testování uživatelského rozhraní**. V tomto bodě se vloží nový kód.  
  
7.  **Upravit podrobnosti akcí testů a kontrolní výrazy**.  
  
     Otevřete UIMap.uitest. Tento soubor se otevře v programových uživatelského rozhraní editoru testu, kde vám může upravit všechny posloupnost akcí, které jste si poznamenali, stejně jako upravit vaše kontrolní výrazy.  
  
     ![Programový Editor testu uživatelského rozhraní](../test/media/cuit_editor_edit.png "CUIT_Editor_edit")  
  
     Další informace najdete v tématu [testů uživatelského rozhraní pro úpravy programový pomocí editoru programových testů uživatelského rozhraní](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).  
  
8.  **Spuštění testu**.  
  
     Pomocí Průzkumníka testů nebo otevřete místní nabídky v metodě testu a pak zvolte **spuštění testů**. Další informace o tom, jak spustit testy najdete v tématu [spouštění testů jednotek pomocí Průzkumníka testů](../test/run-unit-tests-with-test-explorer.md) a *další možnosti pro spuštění programových testů UI* v [co je další?](#VerifyCodeUsingCUITWhatsNext) v části konci tohoto tématu.  
  
 Zbývající části v tomto tématu obsahují další podrobnosti o postupu v tomto postupu.  
  
 Podrobnější příklad najdete v tématu [návod: vytváření, úpravy a údržba programového testu UI](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md). V tomto návodu vytvoříte jednoduchou aplikaci Windows Presentation Foundation (WPF) k ukazují, jak vytvářet, upravovat a udržovat programového testu uživatelského rozhraní. Návod poskytuje řešení pro opravu testů, které byly poškozeny různými chybami časování a refaktoringem ovládacích prvků.
  
###  <a name="starting"></a>Spuštění a zastavení aplikace v rámci testu  
 *Nechci spuštění a zastavení Moje aplikace, prohlížeč nebo databáze zvlášť pro každý test. Jak vyhnout?*  
  
-   ![Prerequsite](../test/media/prereq.png "požadavků") nechcete záznam akcí spusťte aplikaci v testu, musíte spustit aplikace před použitím **záznam** ikonu.  
  
-   ![Prerequsite](../test/media/prereq.png "požadavků")na konci testu, ukončení procesu, ve kterém se test spustí. Pokud jste spustili aplikaci v testu, aplikace se obvykle ukončí.  Pokud nechcete, aby test zavřete aplikaci, když ho ukončí, musíte přidat souboru .runsettings pro vaše řešení a použít `KeepExecutorAliveAfterLegacyRun` možnost. Další informace najdete v tématu [konfigurace testování částí s použitím souboru .runsettings](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md).  
  
-   ![Prerequsite](../test/media/prereq.png "požadavků") můžete přidat testovací Metoda initialize, identifikovanou pomocí atributu [TestInitialize], který spouští kód na začátku každého testu metoda. Například může spustit aplikaci z metody TestInitialize.  
  
-   ![Prerequsite](../test/media/prereq.png "požadavků") můžete přidat testovací metodu čištění, identifikovanou pomocí atributu [TestCleanup], která spustí kód na konci každého testu metoda. Například metoda aplikace se zavře lze volat z TestCleanup metoda.  
  
###  <a name="VerifyingCodeUsingCUITGenerateAssertions"></a>Ověření vlastnosti ovládacích prvků uživatelského rozhraní  
 Můžete použít **programového Tvůrce testování uživatelského rozhraní** přidat uživatelský ovládací prvek rozhraní (UI) pro <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap> testovacího nebo ke generování kódu pro metody ověřování, která používá kontrolní výrazy pro ovládací prvek uživatelského rozhraní.  
  
 Chcete-li vygenerovat kontrolní výrazy pro vaše ovládací prvky uživatelského rozhraní, zvolte **přidat kontrolní výrazy** nástroj v programových Tvůrce testování uživatelského rozhraní a přetáhněte ji do ovládacího prvku na aplikaci v části test, který chcete ověřit správnost. Pokud pole popisuje vlastního ovládacího prvku, tlačítko myši. Řídicí kód třída je okamžitě vytvořen v `UIMap.Designer.cs` souboru.  
  
 ![Cílení na element programového testu UI](../test/media/codedui_1.png "CodedUI_1")  
  
 Vlastnosti pro tento ovládací prvek jsou nyní uvedeny v **přidat kontrolní výrazy** dialogové okno.  
  
 Dalším způsobem, jak přejdete na určitý ovládací prvek je vyberte šipku **(<<)** rozbalte zobrazení **mapy ovládacího prvku uživatelského rozhraní**. Najít nadřazenou, na stejné úrovni nebo podřízený ovládací prvek, můžete klikněte kamkoli na mapě a použijte klávesy se šipkami pohyb stromu.  
  
 ![Programové uživatelského rozhraní testování vlastnosti](../test/media/codedui_2.png "CodedUI_2")  
  
-   *Při výběru ovládacího prvku v mé aplikaci, nebo se nezobrazí ovládacího prvku mapy ovládacího prvku uživatelského rozhraní se nezobrazí žádné vlastnosti.*  
  
     V kódu aplikace ovládací prvek, který chcete ověřit, musí mít jedinečné ID, jako je například atributu HTML ID nebo WPF UId. Možná budete muset aktualizovat kódu aplikace k přidání těchto ID.  
  
 Dále otevřete místní nabídky na vlastnost pro ovládací prvek uživatelského rozhraní, který chcete ověřit a pak přejděte na **přidat kontrolní**. V **přidat kontrolní** dialogové okno, vyberte **Komparátor** pro assertion, například <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A>a zadejte hodnotu pro vaše assertion v **hodnotu porovnání**.  
  
 ![Programové uživatelského rozhraní test kontrolní výrazy](../test/media/codedui_3.png "CodedUI_3")  
  
 Pokud jste přidali všechny kontrolní výrazy testovacího, zvolte **OK**.  
  
 Generování kódu pro vaše kontrolní výrazy a přidání ovládacího prvku do mapy uživatelského rozhraní, vyberte **generovat kód** ikonu. Zadejte název pro metodu programových testů uživatelského rozhraní a popis pro metodu, která budou přidáni jako komentáře pro metodu. Zvolte **přidat a generovat**. V dalším kroku vyberte **zavřete** ikonu zavřete **Tvůrce programového testu uživatelského rozhraní**. To generuje kód podobná následující kód. Například, pokud zadaný název je `AssertForAddTwoNumbers`, kód bude vypadat jako tento ukázkový:  

-   Volání metody assert AssertForAddTwoNumbers přidá metoda test v souboru programového testu uživatelského rozhraní:

    ```csharp
    [TestMethod]  
    public void CodedUITestMethod1()  
    {  
        this.UIMap.AddTwoNumbers();  
        this.UIMap.AssertForAddTwoNumbers();  
    }  
    ```
  
     Můžete upravit tento soubor, chcete-li změnit pořadí kroků a kontrolní výrazy nebo k vytvoření nové metody testu. Chcete-li přidat další kód, místní kurzor na metodě test a v místní nabídce zvolte **generovat kód pro programové testování uživatelského rozhraní**.  
  
-   Přidá metodu s názvem `AssertForAddTwoNumbers` do mapy uživatelského rozhraní (UIMap.uitest). Tento soubor se otevře v programových uživatelského rozhraní editoru testu, kde můžete upravit kontrolní výrazy.  
  
     ![Upravit assert pomocí editoru programových testů UI](../test/media/cuit_editor_assert.png "CUIT_Editor_assert")  
  
     Další informace najdete v tématu [testů uživatelského rozhraní pro úpravy programový pomocí editoru programových testů uživatelského rozhraní](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).  
  
     Generovaný kód metody assertion můžete také zobrazit v UIMap.Designer.cs. Nicméně byste neměli upravovat tento soubor. Pokud chcete, aby přizpůsobena verzi kód, zkopírujte do jiného souboru, jako je například UIMap.cs metody, přejmenování metody a upravovat je.  
  
    ```csharp
    public void AssertForAddTwoNumbers()  
    {  
        ...  
    }  
    ```  
  
 *Ovládací prvek, který chcete vybrat ztratí fokus a zmizí při pokusu vyberte přidat kontrolní výrazy nástroj Tvůrce programového testu uživatelského rozhraní. Postup při výběru ovládacího prvku?*  
 **Výběr skrytý ovládací prvek pomocí klávesnice**  
  
 V některých případech, kdy [přidání ovládacích prvků a ověření jejich vlastnosti](#VerifyingCodeUsingCUITGenerateAssertions), možná budete muset použít klávesnici. Například při pokusu o záznam programového testu uživatelského rozhraní, používající ovládacího prvku nabídka kontextu seznam položek nabídky v ovládacím prvku ztratí fokus a při pokusu o z Tvůrce testování uživatelského rozhraní programového vyberte nástroj přidat kontrolní výrazy zmizí. Tento postup je znázorněn na následujícím obrázku, kde budou v místní nabídce v aplikaci Internet Explorer, ztratí fokus a zmizí, pokud se pokusíte vyberte ho pomocí nástroje přidejte kontrolní výrazy.  
  
 ![CodedUITest &#95; SelectControlKeyboard](../test/media/codeduitest_selectcontrolkeyboard.png "CodedUITest_SelectControlKeyboard")  
  
 Použití klávesnice k výběru ovládacího prvku uživatelského rozhraní, najeďte myší řízení pomocí myši. Podržte stisknutou **Ctrl** klíč a **I** klíče ve stejnou dobu. Uvolnění klíče. Ovládací prvek se zaznamenává pomocí Tvůrce programového testu UT.  
  
> [!WARNING]
>  Pokud používáte Microsoft Lync, je třeba nejprve zavřít Lync spuštění Tvůrce programového testu uživatelského rozhraní. Microsoft Lync naruší **Ctrl + I** klávesové zkratky.  
  
 *Nelze zaznamenávat hover myši v ovládacím prvku. Je možné vyřešit?*  
 **Ruční záznam se ukazatel myši nachází**  
  
 Za určitých okolností konkrétní ovládací prvek, který se používá v programových uživatelského rozhraní test může vyžadovat použití klávesnice k události hover ručně zaznamenávat myši. Například při testování formuláře Windows nebo aplikace pro Windows Presentation Foundation (WPF), mohou existovat vlastní kód. Nebo může být zvláštní chování definované pro ukazatele myši na ovládací prvek, jako je například rozšíření při umístění myši nad ním uzlu stromu. Chcete-li otestovat za těchto okolností, budete muset ručně oznámit, že předdefinované programového uživatelského rozhraní Test tvůrce, který se ukazatele myši na ovládací prvek stisknutím kombinace kláves.  
  
 Při provádění vaší programového testu uživatelského rozhraní, najeďte myší řízení. Stiskněte a podržte klávesu Ctrl, a stisknutím a podržením klávesy Shift a R na klávesnici. Uvolnění klíče. Pomocí Tvůrce programového testu UT se zaznamená událost hover myši.  
  
 ![CodedUI &#95; Najeďte](../test/media/codedui_hover.png "CodedUI_Hover")  
  
 Po vygenerování testu metoda, podobně jako v následujícím příkladu kódu budou přidány do souboru UIMap.Desinger.cs:  
  
```csharp  
// Mouse hover '1' label at (87, 9)  
Mouse.Hover(uIItem1Text, new Point(87, 9));  
  
```  
  
 *Přiřazení klíče pro zachycení událostí myši hover se používá jinde v mé prostředí. Můžete změnit přiřazení klíče výchozí?*  
 **Konfigurování přiřazení klávesnice hover myši**  
  
 V případě potřeby přiřazení klávesnice výchozí Ctrl + Shift + R, který se používá k aplikování výběru ukázáním události myši ve vašich programových testech uživatelského rozhraní lze nakonfigurovat k využívání různé klíče.  
  
> [!WARNING]
>  Chcete-li změnit přiřazení klávesnice pro události myši hover za běžných okolností by neměl mít vám. Při opětovné přiřazování přiřazení klávesnice buďte opatrní. Svou volbu mohou být již používán jinde v rámci sady Visual Studio nebo v aplikaci během testování.  
  
 Chcete-li změnit přiřazení klávesnice, je třeba upravit následující konfigurační soubor:  
  
 `<drive letter:>\Program Files (x86)\Microsoft Visual Studio 11.0\Common7\IDE\CodedUITestBuilder.exe.config`  
  
 V konfiguračním souboru, změňte hodnoty `HoverKeyModifier` a `HoverKey` klávesy se šipkami upravte přiřazení klávesové:  
  
```
<!-- Begin : Background Recorder Settings -->  
<!-- HoverKey to use. -->  
<add key="HoverKeyModifier" value="Control, Shift"/>  
<add key="HoverKey" value="R"/>  
```
  
 *Mám problémy s záznam umístění ukazatele myši na webu. Je k dispozici oprava v takovém případě příliš?*  
 **Nastavení se implicitní ukazatel myši nachází pro webový prohlížeč**  
  
 V mnoha webů po přesunutí ukazatele myši určitý ovládací prvek, se rozbalí a zobrazí se další podrobnosti. Obecně platí vypadají podobně jako nabídky v aplikací klasické pracovní plochy. Protože je to běžné vzor, povolit programové testy uživatelského rozhraní implicitní umístění ukazatele pro procházení webu. Například pokud je záznam bude umístěn v aplikaci Internet Explorer, je aktivována událost. Tyto události může vést k redundantní umístění ukazatele získávání zaznamenávají. Z toho důvodu se zaznamenávají implicitní umístění ukazatele s `ContinueOnError` nastavena na `true` v konfiguračním souboru testu uživatelského rozhraní. To umožňuje přehrávání Chcete-li pokračovat, pokud událost hover se nezdaří.  
  
 Pokud chcete povolit záznamu implicitní umístění ukazatele ve webovém prohlížeči, otevřete konfigurační soubor:  
  
 `<drive letter:>\Program Files (x86)\Microsoft Visual Studio 11.0\Common7\IDE\CodedUITestBuilder.exe.config`  
  
 Ověřte, zda konfigurační soubor obsahuje klíč `RecordImplicitiHovers` nastavena na na hodnotu `true` jak znázorňuje následující ukázka:  
  
```  
<!--Use this to enable/disable recording of implicit hovers.-->  
<add key="RecordImplicitHover" value="true"/>  
  
```  
  
##  <a name="VerifyingCodeCUITModify"></a>Přizpůsobení vaší programového testu uživatelského rozhraní  
 Po vytvoření vaší programového testu uživatelského rozhraní, můžete ji upravit pomocí některé z následujících nástrojů v sadě Visual Studio:  
  
-   **Programový Tvůrce testu uživatelského rozhraní:** pomocí Tvůrce programového testu uživatelského rozhraní můžete přidat další ovládací prvky a ověření do testů. Najdete v části [přidání ovládacích prvků a ověření jejich vlastnosti](#VerifyingCodeUsingCUITGenerateAssertions) v tomto tématu.  
  
-   **Programový Editor testu uživatelského rozhraní:** editoru programového testu uživatelského rozhraní umožňuje snadno upravovat programových testů uživatelského rozhraní. Pomocí editoru testování uživatelského rozhraní programového, můžete vyhledat, zobrazit a upravit zkušební metody. Můžete taky upravit akcí uživatelského rozhraní a jejich přidružených ovládacích prvcích v mapě ovládací prvek uživatelského rozhraní. Další informace najdete v tématu [testů uživatelského rozhraní pro úpravy programový pomocí editoru programových testů uživatelského rozhraní](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md).  
  
-   **Editor kódu:**  
  
    -   Ručně přidejte kód pro ovládací prvky v testu, jak je popsáno v [kódování uživatelského rozhraní řízení akcí a vlastností](#VerifyingCodeCUITActionsandProperties) v tomto tématu.  
  
    -   Po vytvoření programového testu uživatelského rozhraní, můžete upravit mohla být řízené daty. Další informace najdete v tématu [vytváření Data-Driven programového testu uživatelského rozhraní](../test/creating-a-data-driven-coded-ui-test.md).  
  
    -   V programových přehrávání testu uživatelského rozhraní můžete určit, aby test čekání na určité události proběhnout, jako je například okno se zobrazí indikátor průběhu zmizet a tak dále. K tomu, přidejte příslušnou metodu UITestControl.WaitForControlXXX(). Úplný seznam dostupných metod najdete v tématu [provedení programového uživatelského rozhraní testy počkejte pro konkrétní události při přehrávání](../test/making-coded-ui-tests-wait-for-specific-events-during-playback.md). Příklad programového testu uživatelského rozhraní, který čeká ovládacího prvku povolení metodou WaitForControlEnabled, naleznete v části [návod: vytváření, úpravy a údržba programového uživatelského rozhraní testovací](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md).  
  
    -   Programové testy uživatelského rozhraní zahrnují podporu pro některé z ovládacích prvků HTML5, které jsou součástí aplikace Internet Explorer 9 a Internet Explorer 10. Další informace najdete v tématu [pomocí ovládacích prvků HTML5 v programových testů uživatelského rozhraní](../test/using-html5-controls-in-coded-ui-tests.md).  
  
    -   **Kódování pokyny programového testu uživatelského rozhraní:**  
  
        -   [Anatomie programového testu UI](../test/anatomy-of-a-coded-ui-test.md)  
  
        -   [Doporučené postupy pro programové testy UI](../test/best-practices-for-coded-ui-tests.md)  
  
        -   [Testování rozsáhlé aplikace s více mapami uživatelského rozhraní](../test/testing-a-large-application-with-multiple-ui-maps.md)  
  
        -   [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)  
  
###  <a name="generatedCode"></a>Generovaný kód  
 Pokud vyberete **generovat kód**, se vytvářejí několika částí kódu:  
  
-   **Řádek v metodě testu.**  
  
    ```csharp  
    [CodedUITest]  
    public class CodedUITest1  
    { ...  
      [TestMethod]  
      public void CodedUITestMethod1()  
      {  
          this.UIMap.AddTwoNumbers();  
          // To generate more code for this test, select   
          // "Generate Code" from the shortcut menu.      }  
    }  
    ```  
  
     Klikněte pravým tlačítkem v této metodě, chcete-li přidat více zaznamenané akce a ověření. Můžete také upravit jeho ručně rozšířit nebo změnit kód. Například některé kódu může uzavřít ve smyčce.  
  
     Můžete také přidat nové metody test a přidejte kód k nim stejným způsobem. Každá metoda test musí mít `[TestMethod]` atribut.  
  
-   **Metoda v UIMap.uitest**  
  
     Tato metoda obsahuje podrobnosti o akce, které jste si poznamenali nebo hodnotu, která jste ověřili. Tento kód můžete upravit tak, že otevřete UIMap.uitest. Otevře se v specializované editor, ve kterém můžete odstranit nebo Refaktorovat zaznamenaných akcí.  
  
     Vygenerovaný metoda Youcan také zobrazit v UIMap.Designer.cs. Tato metoda provádí akce, že jste si poznamenali při spuštění testu.  
  
    ```csharp  
    // File: UIMap.Designer.cs  
    public partial class UIMap  
    {  
      /// <summary>  
      /// Add two numbers  
      /// </summary>  
      public void AddTwoNumbers()  
      { ...   }  
    }  
    ```  
  
    > [!WARNING]
    >  Tento soubor by neměl upravit, protože se znovu vygeneruje, když vytvoříte další testy.  
  
     Přizpůsobena verze těchto metod můžete nastavit zkopírováním do UIMap.cs. Například můžete dokonce vytvářet parametrizované verzi, která může volat z metody testu:  
  
    ```csharp  
    // File: UIMap.cs  
    public partial class UIMap // Same partial class  
    {  
      /// <summary>  
      /// Add two numbers - parameterized version  
      /// </summary>  
      public void AddTwoNumbers(int firstNumber, int secondNumber)  
      { ...   // Code modified to use parameters.  
      }  
    }  
    ```  
  
-   **Deklarace v UIMap.uitest**  
  
     Tyto deklarace představují ovládací prvky uživatelského rozhraní aplikace, které jsou používány svůj test. Používají se podle generovaný kód pro provoz ovládací prvky a přístup k jejich vlastnosti.  
  
     Můžete taky je můžete psát vlastní kód. Například můžete mít metodu testu zvolte hypertextový odkaz ve webové aplikaci, zadejte hodnotu v textovém poli, nebo větev a provádět různé akce testování na základě hodnoty v poli.  
  
     Můžete přidat více programové testy uživatelského rozhraní a více map – objekty uživatelského rozhraní a souborů usnadňuje testování rozsáhlé aplikace. Další informace najdete v tématu [testování rozsáhlé aplikace s více mapami uživatelského rozhraní](../test/testing-a-large-application-with-multiple-ui-maps.md).  
  
 Další informace o generovaného kódu najdete v tématu [anatomie programového testu uživatelského rozhraní](../test/anatomy-of-a-coded-ui-test.md).  
  
###  <a name="actions"></a>Kódování uživatelského rozhraní řízení akcí a vlastností  
 Při práci s ovládacími prvky testu uživatelského rozhraní v programové testy uživatelského rozhraní, které jsou rozdělené do dvou částí: akcí a vlastností.  
  
-   První část se skládá z akcí, které můžete provádět na ovládacích prvků uživatelského rozhraní test. Programové testy uživatelského rozhraní můžete například simulovat kliknutí myší na ovládací prvek testu uživatelského rozhraní nebo simulovat klíče zadali na klávesnici ovlivnit prvku testu uživatelského rozhraní.  
  
-   Druhá část se skládá z umožňuje načíst a nastavit vlastnosti v ovládacím prvku testu uživatelského rozhraní. Například programové testy uživatelského rozhraní můžete získat počet položek v `ListBox`, nebo nastavte `CheckBox` na vybraném stavu.  
  
 **Přístup k akce řízení testu uživatelského rozhraní**  
  
 K provádění akcí na ovládacích prvků testu uživatelského rozhraní, jako je například kliknutí myší, nebo akce, klávesnice, pomocí metod v nástroji <xref:Microsoft.VisualStudio.TestTools.UITesting.Mouse> a <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard> třídy:  
  
-   Pokud chcete provést orientované myši akce, například myši klikněte na ovládací prvek testu uživatelského rozhraní, použijte <xref:Microsoft.VisualStudio.TestTools.UITesting.Mouse.Click%2A>.  
  
     `Mouse.Click(buttonCancel);`  
  
-   K provedení akce orientované na klávesnici, jako je například psaní do ovládacího prvku úprav použít <xref:Microsoft.VisualStudio.TestTools.UITesting.Keyboard.SendKeys%2A>.  
  
     `Keyboard.SendKeys(textBoxDestination, @"C:\Temp\Output.txt");`  
  
 **Přístup k vlastnostem řízení testu uživatelského rozhraní**  
  
 K získání a nastavení konkrétní hodnoty vlastnosti kontrolní mechanismus uživatelského rozhraní, můžete přímo získání nebo nastavení hodnoty vlastnosti ovládacího prvku, nebo můžete použít <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.GetProperty%2A?displayProperty=fullName> a <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.SetProperty%2A?displayProperty=fullName> metody s názvem konkrétní vlastnosti, které chcete získat nebo nastavit.  
  
 <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.GetProperty%2A>Vrátí objekt, který lze převést na příslušné <xref:System.Type>. <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.SetProperty%2A>přijme objekt pro hodnotu vlastnosti.  
  
##### <a name="to-get-or-set-properties-from-ui-test-controls-directly"></a>Pro získání nebo nastavení vlastností přímo z ovládacích prvků testu uživatelského rozhraní  
  
-   Pomocí ovládacích prvků, které jsou odvozeny od T:Microsoft.VisualStudio.TestTools.UITesting.UITestControl, jako je například T:Microsoft.VisualStudio.TestTools.UITesting.HtmlControls.HtmlList nebo T: Microsoft.VisualStudio.TestTools.UITesting.WinControls.WinComboBox, můžete získat nebo nastavit jejich hodnoty vlastností přímo, a to takto:  
  
    ```csharp
    int i = myHtmlList.ItemCount;  
    myWinCheckBox.Checked = true;  
    ```  
  
##### <a name="to-get-properties-from-ui-test-controls"></a>Chcete-li získat vlastnosti z ovládacích prvků testu uživatelského rozhraní  
  
-   Chcete-li získat hodnotu vlastnosti z ovládacího prvku, použijte <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.GetProperty%2A>.  
  
-   Pokud chcete nastavit vlastnost ovládacího prvku získat, použijte příslušným řetězcem z `PropertyNames` třídy v každý ovládací prvek jako parametr pro <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.GetProperty%2A>.  
  
-   <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.GetProperty%2A>Vrátí příslušný datový typ, ale to vrátit hodnotu vložena jako <xref:System.Object>. Návratový <xref:System.Object> musí přetypovat jako příslušného typu.  
  
     Příklad:  
  
     `int i = (int)GetProperty(myHtmlList.PropertyNames.ItemCount);`  
  
##### <a name="to-set-properties-for-ui-test-controls"></a>Nastavení vlastností pro testování uživatelského rozhraní ovládacích prvků  
  
-   Pokud chcete nastavit vlastnost v ovládacím prvku, použijte <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.SetProperty%2A>.  
  
-   Pokud chcete nastavit vlastnost ovládacího prvku nastavit, použijte příslušným řetězcem z `PropertyNames` třída jako první parametr <xref:Microsoft.VisualStudio.TestTools.UITesting.UITestControl.SetProperty%2A>, se hodnota vlastnosti jako druhý parametr.  
  
     Příklad:  
  
     `SetProperty(myWinCheckBox.PropertyNames.Checked, true);`  
  
###  <a name="debugging"></a>Ladění  
 Můžete analyzovat testů programového uživatelského rozhraní pomocí protokolů programové testování uživatelského rozhraní. Programových filtru protokoly testu uživatelského rozhraní a záznam, který spouští důležité informace o vaší programového testu uživatelského rozhraní. Formát protokoly umožňuje rychle ladění problémů. Další informace najdete v tématu [analýza programových testů pomocí programových uživatelského rozhraní protokolů z těchto testů](../test/analyzing-coded-ui-tests-using-coded-ui-test-logs.md).  
  
##  <a name="VerifyCodeUsingCUITWhatsNext"></a>Co je další?  
 **Další možnosti pro spuštění programových testů uživatelského rozhraní:** programové testy uživatelského rozhraní můžete spustit přímo ze sady Visual Studio, jak je popsáno výše v tomto tématu. Kromě toho můžete spustit automatizovaných testů uživatelského rozhraní z [!INCLUDE[TCMext](../misc/includes/tcmext_md.md)], nebo z [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)]. Pokud jsou automatizované programové testy uživatelského rozhraní, mají při spuštění, na rozdíl od jiných automatizovaných testů komunikovat s plochou.  
  
-   [Postupy: spouštění testů ze sady Microsoft Visual Studio](http://msdn.microsoft.com/Library/1a1207a9-2a33-4a1e-a1e3-ddf0181b1046)  
  
-   [Spuštění automatizovaných testů v nástroji Microsoft Test Manager](http://msdn.microsoft.com/en-us/0632f265-63fe-4859-a413-9bb934c66835)  
  
-   [Postupy: Konfigurace a spouštění plánovaných testů po sestavení aplikace](http://msdn.microsoft.com/en-us/32acfeb1-b1aa-4afb-8cfe-cc209e6183fd)  
  
-   [Spouštění testů v procesu sestavení](http://msdn.microsoft.com/Library/d05743a1-c5cf-447e-bed9-bed3cb595e38)
  
-   [Postupy: nastavení agenta Test Agent pro spouštění testů komunikujících s plochou](http://msdn.microsoft.com/Library/3a94dd07-6d17-402c-ae8f-7947143755c9)
  
 **Přidání podpory pro vlastní ovládací prvky:** rámci programové testování uživatelského rozhraní nepodporuje všechny možné uživatelského rozhraní a nemusí podporovat uživatelského rozhraní, kterou chcete otestovat. Například nelze okamžitě vytvořit programového testu UI uživatelského rozhraní pro [!INCLUDE[ofprexcel](../test/includes/ofprexcel_md.md)]. Můžete však vytvořit rozšíření pro programové testování framework uživatelského rozhraní, která bude podporovat vlastního ovládacího prvku.  
  
-   [Povolení programového testování uživatelského rozhraní pro vaše ovládací prvky](../test/enable-coded-ui-testing-of-your-controls.md)  
  
-   [Rozšiřování programových testů UI a záznamů akcí k podpoře Microsoft Excel](../test/extending-coded-ui-tests-and-action-recordings-to-support-microsoft-excel.md)  
  
 Programové testy uživatelského rozhraní se často používají k automatizaci manuálních testů. Další informace najdete v části [testování pro nastavené průběžné doručování s Visual Studio 2012 – kapitoly 5: automatizace systémových testů](http://go.microsoft.com/fwlink/?LinkID=255196). Další informace o ruční testy najdete v tématu [spouštění manuálních testů pomocí nástroje Microsoft Test Manager](/vsts/manual-test/mtm/run-manual-tests-with-microsoft-test-manager). Další informace o automatizované systémové testy najdete v tématu [vytváření automatizovaných testů pomocí nástroje Microsoft Test Manager](http://msdn.microsoft.com/en-us/7b5075ee-ddfe-411d-b1d4-94283550a5d0).  
  
## <a name="external-resources"></a>Externí zdroje  
  
### <a name="guidance"></a>Doprovodné materiály  
 [Testování pro nastavené průběžné doručování s Visual Studio 2012 – kapitoly 2: testování částí: testování uvnitř](http://go.microsoft.com/fwlink/?LinkID=255188)  
  
 [Testování pro nastavené průběžné doručování s Visual Studio 2012 – kapitoly 5: automatizace systémových testů](http://go.microsoft.com/fwlink/?LinkID=255196)  
  
### <a name="faq"></a>Nejčastější dotazy  
 [Časté otázky – 1 testy programové uživatelského rozhraní](http://go.microsoft.com/fwlink/?LinkID=230576)  
  
 [Programové testy UI -2 – nejčastější dotazy](http://go.microsoft.com/fwlink/?LinkID=230578)  
  
### <a name="forum"></a>Fórum  
 [Visual Studio testování uživatelského rozhraní automatizace (zahrnuje CodedUI)](http://go.microsoft.com/fwlink/?LinkID=224497)  
  
## <a name="see-also"></a>Viz také  
 <xref:Microsoft.VisualStudio.TestTools.UITest.Common.UIMap.UIMap>   
 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>   
 [Zlepšení kvality kódu](../test/improve-code-quality.md)   
 [Návod: Vytváření, úpravy a údržba programového testu UI](../test/walkthrough-creating-editing-and-maintaining-a-coded-ui-test.md)   
 [Anatomie programového testu UI](../test/anatomy-of-a-coded-ui-test.md)   
 [Osvědčené postupy pro programové testy uživatelského rozhraní](../test/best-practices-for-coded-ui-tests.md)   
 [Testování rozsáhlé aplikace s více mapami uživatelského rozhraní](../test/testing-a-large-application-with-multiple-ui-maps.md)   
 [Úpravy programových testů uživatelského rozhraní pomocí editoru programových testů UI](../test/editing-coded-ui-tests-using-the-coded-ui-test-editor.md)   
 [Podporované konfigurace a platformy pro programové testy uživatelského rozhraní a zaznamenávání akcí](../test/supported-configurations-and-platforms-for-coded-ui-tests-and-action-recordings.md)   
 [Upgrade programových testů UI z produktu Visual Studio 2010](../test/upgrading-coded-ui-tests-from-visual-studio-2010.md)
