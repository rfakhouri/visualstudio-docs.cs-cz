---
title: "Přizpůsobení Element vytváření a přesun | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.dsltools.dsldesigner.elementmergedirective
helpviewer_keywords: Domain-Specific Language, element merge directives
ms.assetid: cbd28f15-dfd7-46bd-ab79-5430e3ed83c8
caps.latest.revision: "36"
author: alancameronwills
ms.author: awills
manager: douge
ms.openlocfilehash: d678e05046a367a722a586d13a50ef7bf0aabc79
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="customizing-element-creation-and-movement"></a>Přizpůsobení vytvoření a přesunutí elementu
Můžete povolit element být přetažen na jiné, z panelu nástrojů nebo v vkládání nebo operace přesunutí. Můžete mít přesunutý elementy propojené s cílových elementů, pomocí vztahy, které zadáte.  
  
 K elementu sloučení – direktiva (EMD) určuje, co se stane, když jeden element modelu *sloučené* do elementu jiného modelu. To se stane, když:  
  
-   Uživatel nastavuje tažením z panelu nástrojů na diagram nebo obrazce.  
  
-   Uživatel vytvoří element pomocí nabídky přidat v Průzkumníku nebo obrazce prostředí.  
  
-   Uživatel přesune položku z jedné dráze na jiný.  
  
-   Uživatel vloží elementu.  
  
-   Váš kód programu volá sloučení direktivu element.  
  
 I když se operace vytvoření se může zdát, že se liší od operace kopírování, ve skutečnosti fungují stejným způsobem. Když se přidá element, například z panelu nástrojů prototyp ho se replikují. Prototyp je stejným způsobem jako elementy, které byly zkopírovány z jiné části modelu sloučeny do modelu.  
  
 Je zodpovědností EMD je k rozhodování o tom, jak objekt nebo skupinu objektů, které by měly být sloučeny do konkrétního umístění v modelu. Konkrétně rozhodne, jaké relace musí být vytvořena instance propojení skupině sloučené do modelu. Můžete také upravit, je možné nastavit vlastnosti a vytvořit další objekty.  
  
 ![DSL & č. 45; EMD &#95; Sloučení](../modeling/media/dsl-emd_merge.png "DSL EMD_Merge")  
Role sloučení direktivu Element  
  
 EMD je vytvořen automaticky, když definujete vnoření vztah. Toto výchozí nastavení EMD vytvoří instance vztahu, když uživatelé přidají nové instance podřízené do nadřazené. Tyto výchozí EMDs, můžete upravit třeba tak, že přidáte vlastní kód.  
  
 Můžete také přidat vlastní EMDs v definici DSL tak, aby uživatelé přetáhněte nebo vložit různé kombinace třídy sloučené a příjmu.  
  
## <a name="defining-an-element-merge-directive"></a>Definování direktivu Element sloučení  
 Element sloučení direktivy můžete přidat do třídy domény, relace domény, tvarů, konektory a diagramy. Můžete přidat nebo je najít v Průzkumníku DSL pod přijímající třídou domény. Přijímající třídy je třída domény elementu, který už v modelu a do které budou sloučeny element nové nebo zkopírovaný.  
  
 ![DSL & č. 45; EMD &#95; podrobnosti](../modeling/media/dsl-emd_details.png "DSL EMD_Details")  
  
 **Indexování třída** je třída domény elementů, které mohou být sloučeny do členy přijímající třídy. Instance podtřídami třídy indexování bude být také sloučit tak, že tento EMD, není-li nastavena **platí pro podtřídy** na hodnotu False.  
  
 Existují dva druhy direktiva sloučení:  
  
-   A **proces sloučení** – direktiva určuje vztahy, které musí být propojena nového elementu do stromu.  
  
-   A **dál sloučení** – direktiva přesměruje na jiný přijímající element, obvykle nadřazený nového elementu.  
  
 Můžete přidat vlastní kód sloučit direktivy:  
  
-   Nastavit **používá vlastní přijmout** přidat vlastní kód pro určení, zda by měly být konkrétní instanci indexování element sloučeny do cílového elementu. Když uživatel nastavuje tažením z panelu nástrojů, "neplatný" ukazatel zobrazí, pokud kód zakáže sloučení.  
  
     Může například umožňuje sloučení, jenom v případě, že přijímající elementu je v určitém stavu.  
  
-   Nastavit **používá vlastní sloučení** přidat zadejte vlastní kód, který definuje změny, které jsou vytvářeny do modelu, když se provádí sloučení.  
  
     Můžete například nastavit vlastnosti v elementu sloučené pomocí dat z nového umístění v modelu.  
  
> [!NOTE]
>  Pokud píšete kód vlastní sloučení, ovlivňuje pouze sloučení, které se provádějí pomocí této EMD. Pokud existují další EMDs, které sloučení stejný typ objektu, nebo pokud je jiný vlastní kód, který vytvoří tyto objekty bez použití EMD, nebude vliv podle kódu vlastní sloučení.  
>   
>  Pokud chcete zajistit, že nového elementu nebo nové relace vždy zpracovává vlastní kód, vezměte v úvahu definování `AddRule` v vnoření relaci a `DeleteRule` na třídě domény elementu. Další informace najdete v tématu [pravidla rozšíří změny v rámci modelu](../modeling/rules-propagate-changes-within-the-model.md).  
  
## <a name="example-defining-an-emd-without-custom-code"></a>Příklad: Definování EMD bez vlastního kódu  
 V následujícím příkladu umožní uživatelům vytvářet element a konektor ve stejnou dobu tak, že přetáhnete z panelu nástrojů na existující tvar. V příkladu se přidá EMD k definici DSL. Před tato úprava uživatelů můžete přetáhnout nástroje do diagramu, ale ne na existující obrazce.  
  
 Uživatelům také můžete vložit prvků na další prvky.  
  
#### <a name="to-let-users-create-an-element-and-a-connector-at-the-same-time"></a>Umožníte uživatelům vytvářet element a konektor ve stejnou dobu  
  
1.  Vytvořit nový DSL pomocí **minimální jazyk** šablona řešení.  
  
     Když spustíte tento DSL, umožňuje vám vytvořit tvarů a konektory mezi obrazce. Nelze přetáhnout novou **ExampleElement** tvaru z panelu nástrojů na existující tvar.  
  
2.  Aby mohli uživatelé sloučit elementy na `ExampleElement` tvarů, vytvořte novou EMD v `ExampleElement` domény – třída:  
  
    1.  V **DSL Explorer**, rozbalte položku **domény třídy**. Klikněte pravým tlačítkem na `ExampleElement` a pak klikněte na **přidejte nový Element sloučení – direktiva**.  
  
    2.  Ujistěte se, že **DSL podrobnosti** je otevřeno, tak, aby se zobrazí podrobnosti o nové EMD. (Nabídky: **zobrazení**, **jinými**, **DSL podrobnosti**.)  
  
3.  Nastavte **indexování třída** v okně podrobností DSL definovat, jaké třída elementů by se daly sloučit do `ExampleElement` objekty.  
  
     V tomto příkladu vyberte `ExampleElements`tak, aby uživatel můžete přetáhnout nové prvky na stávající elementy.  
  
     Všimněte si, že třída indexování bude název EMD v Průzkumníku DSL.  
  
4.  V části **proces sloučení vytvořením odkazy**, přidejte dvě cesty:  
  
    1.  Jedna cesta odkazuje na nadřazeném modelu nového elementu. Výraz cesty, které je třeba zadat přejde na z existujícího elementu, až vnoření vztah k nadřazené modelu. Nakonec Určuje roli v nový odkaz, ke kterému se přiřadí nového elementu. Cesta je následující:  
  
         `ExampleModelHasElements.ExampleModel/!ExampleModel/.Elements`  
  
    2.  Jiné cesty propojí nového elementu do existujícího elementu. Výraz cesty určuje referenční vztah a role, ke kterému se přiřadí nového elementu. Tato cesta je následující:  
  
         `ExampleElementReferencesTargets.Sources`  
  
     Nástroj navigační cestu můžete vytvořit jednotlivé cesty:  
  
    1.  V části **proces sloučení vytvořením odkazy na cesty**, klikněte na tlačítko  **\<přidat cestu >**.  
  
    2.  Klikněte na šipku rozevíracího seznamu vedle položky seznamu. Zobrazí se zobrazení stromu.  
  
    3.  Rozbalte uzly ve stromu na formuláři, kterou chcete zadat cestu.  
  
5.  Testovací DSL:  
  
    1.  Stisknutím klávesy F5 znovu sestavte a spusťte řešení.  
  
         Opětovné sestavení bude trvat déle než obvykle, protože generovaný kód se budou aktualizovat z textové šablony tak, aby odpovídala nové definice DSL.  
  
    2.  Když experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] má začít, otevřete soubor modelu z vaší DSL. Vytvořte některé prvky příklad.  
  
    3.  Přetáhněte z **příklad Element** nástroj do existujícího tvaru.  
  
         Se zobrazí nový tvar, a je propojen existující obrazce pomocí konektoru.  
  
    4.  Zkopírujte existující tvar. Vyberte jiný tvar a vložit.  
  
         Vytvoří se kopie na první z nich.  Má nový název a je propojen druhý obrazce pomocí konektoru.  
  
 Všimněte si následujících bodů z tento postup:  
  
-   Vytvořením – Element direktivy sloučení můžete povolit všechny třídy elementu všemi ostatními přijmout. EMD se vytvoří ve třídě přijímající domény, a třída akceptovanou doménu je určena **Index – třída** pole.  
  
-   Definování cesty, můžete určit, jaké odkazy by měl použít pro připojení nového elementu k existující model.  
  
     Odkazy, které zadáte, by měly obsahovat jeden vztah vnoření.  
  
-   EMD ovlivňuje i vytvoření sady nástrojů a také operace vložení.  
  
     Pokud si napsat vlastní kód, který vytváří nové prvky, můžete vyvolat EMD explicitně pomocí `ElementOperations.Merge` metoda. Tím je zajištěno, že váš kód odkazuje nových elementů do modelu stejným způsobem jako jiné operace. Další informace najdete v tématu [přizpůsobení chování kopie](../modeling/customizing-copy-behavior.md).  
  
## <a name="example-adding-custom-accept-code-to-an-emd"></a>Příklad: Přidání do EMD přijmout vlastní kód  
 Můžete přidat vlastní kód ke EMD, můžete definovat složitější chování sloučení. Tento jednoduchý příklad zabrání uživatele přidat více než pevný počet elementů do diagramu. V příkladu změní výchozí EMD, který doprovází vnoření vztah.  
  
#### <a name="to-write-custom-accept-code-to-restrict-what-the-user-can-add"></a>Psaní kódu přijmout vlastní omezit, co uživatel může přidávat  
  
1.  Vytvoření DSL pomocí **minimální jazyk** šablona řešení. Otevřete diagram DSL definice.  
  
2.  V Průzkumníku DSL rozbalte **domény třídy**, `ExampleModel`, **Element sloučení direktivy**. Vyberte sloučení direktivu element, který je pojmenován `ExampleElement`.  
  
     Jak uživatel může vytvořit nové ovládací prvky tento EMD `ExampleElement` objekty v modelu, třeba tak, že přetáhnete z panelu nástrojů.  
  
3.  V **DSL podrobnosti** vyberte **používá vlastní přijmout**.  
  
4.  Znovu sestavte řešení. Bude to trvat déle než obvykle, protože generovaný kód se budou aktualizovat z modelu.  
  
     Chyby sestavení bude hlášené, podobně jako: "Company.ElementMergeSample.ExampleElement neobsahuje definici pro CanMergeExampleElement..."  
  
     Je nutné implementovat metodu `CanMergeExampleElement`.  
  
5.  Vytvoření nového souboru kódu v **Dsl** projektu. Nahraďte jeho obsah následujícím kódem a změnit obor názvů do oboru názvů vašeho projektu.  
  
    ```csharp  
    using Microsoft.VisualStudio.Modeling;  
  
    namespace Company.ElementMergeSample // EDIT.  
    {  
      partial class ExampleModel  
      {  
        /// <summary>  
        /// Called whenever an ExampleElement is to be merged into this ExampleModel.  
        /// This happens when the user pastes an ExampleElement  
        /// or drags from the toolbox.  
        /// Determines whether the merge is allowed.  
        /// </summary>  
        /// <param name="rootElement">The root element in the merging EGP.</param>  
        /// <param name="elementGroupPrototype">The EGP that the user wants to merge.</param>  
        /// <returns>True if the merge is allowed</returns>  
        private bool CanMergeExampleElement(ProtoElementBase rootElement, ElementGroupPrototype elementGroupPrototype)  
        {  
          // Allow no more than 4 elements to be added:  
          return this.Elements.Count < 4;  
        }  
      }  
    }  
  
    ```  
  
     Tento jednoduchý příklad omezuje počet elementů, které by se daly sloučit do nadřazené modelu. Metoda může zajímavějšího podmínky, na základě jakékoli vlastnosti a odkazy přijímající objektu. Ho můžete také prohlédnout vlastnosti slučovat elementy, které se přenášejí v <xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype>. Další informace o `ElementGroupPrototypes`, najdete v části [přizpůsobení chování kopie](../modeling/customizing-copy-behavior.md). Další informace o tom, jak napsat kód, který čte modelu najdete v tématu [navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md).  
  
6.  Testovací DSL:  
  
    1.  Stisknutím klávesy F5 znovu sestavte řešení. Když experimentální instanci [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] otevře, spusťte instanci vaše DSL.  
  
    2.  Vytvoření nových elementů několika způsoby:  
  
        1.  Přetáhněte z **příklad Element** nástroj do diagramu.  
  
        2.  V **příklad Průzkumníka modelu**, klikněte pravým tlačítkem na kořenový uzel a pak klikněte na tlačítko **přidejte nový Element příklad**.  
  
        3.  Zkopírujte a vložte element v diagramu.  
  
    3.  Ověřte, že nemůžete použít žádnou z těchto způsobů, jak přidat více než čtyři elementy do modelu. Je to proto, že všechny používají sloučení direktivu Element.  
  
## <a name="example-adding-custom-merge-code-to-an-emd"></a>Příklad: Přidání do EMD sloučení vlastní kód  
 V kódu vlastní sloučení můžete definovat, co se stane, když uživatel nastavuje tažením nástroj nebo vloží do elementu. Existují dva způsoby, jak definovat vlastní sloučení:  
  
1.  Nastavit **používá vlastní sloučení** a zadejte požadované kódu. Váš kód nahradí kód vygenerovaný sloučení. Tuto možnost použijte, pokud chcete úplně předefinovat, jaké sloučení.  
  
2.  Přepsání `MergeRelate` metoda a volitelně `MergeDisconnect` metoda. Chcete-li to provést, musíte nastavit **generuje dvojité odvozené** vlastnost třídy domény. Váš kód může volat kód vygenerovaný sloučení v základní třídě. Tuto možnost použijte, pokud chcete provést další operace po nebylo provedeno sloučení.  
  
 Tyto přístupy ovlivňují jenom sloučení, které se provádějí pomocí této EMD. Pokud chcete mít vliv na všechny způsoby, ve kterých lze vytvořit sloučené elementu, Alternativně lze definovat `AddRule` v vnoření relaci a `DeleteRule` k třídě sloučené domény. Další informace najdete v tématu [pravidla rozšíří změny v rámci modelu](../modeling/rules-propagate-changes-within-the-model.md).  
  
#### <a name="to-override-mergerelate"></a>Chcete-li přepsat MergeRelate  
  
1.  V definici DSL Ujistěte se, že jste definovali EMD, do které chcete přidat kód. Pokud chcete, můžete přidat cesty a definovat vlastní přijmout kódu, jak je popsáno v předchozí části.  
  
2.  V diagramu DslDefinition vyberte přijímající třídu sloučení. Obvykle je třída na konci zdroj vnoření relace.  
  
     Například v DSL, generují z řešení minimální jazyk, vyberte `ExampleModel`.  
  
3.  V **vlastnosti** nastavte **generuje dvojité odvozené** k **true**.  
  
4.  Znovu sestavte řešení.  
  
5.  Zkontrolujte obsah **Dsl\Generated Files\DomainClasses.cs**. Hledání s názvem metody `MergeRelate` a zkontrolujte jejich obsah. Můžete tak psát vlastní verze.  
  
6.  Do nového souboru kódu zápisu pro třídu přijímající konkrétní třídu a přepsat `MergeRelate` metoda. Nezapomeňte volat základní metodu. Příklad:  
  
    ```csharp  
    partial class ExampleModel  
    {  
      /// <summary>  
      /// Called when the user drags or pastes an ExampleElement onto the diagram.  
      /// Sets the time of day as the name.  
      /// </summary>  
      /// <param name="sourceElement">Element to be added</param>  
      /// <param name="elementGroup">Elements to be merged</param>  
      protected override void MergeRelate(ModelElement sourceElement, ElementGroup elementGroup)  
      {  
        // Connect the element according to the EMD:  
        base.MergeRelate(sourceElement, elementGroup);  
  
        // Custom actions:   
        ExampleElement mergingElement = sourceElement as ExampleElement;  
        if (mergingElement != null)  
        {  
          mergingElement.Name = DateTime.Now.ToLongTimeString();  
        }  
      }  
    }  
  
    ```  
  
#### <a name="to-write-custom-merge-code"></a>Napsat sloučení vlastní kód  
  
1.  V **Dsl\Generated Code\DomainClasses.cs**, zkontrolujte metody s názvem `MergeRelate`. Tyto metody vytvoření propojení mezi nového elementu a existující model.  
  
     Také zkontrolujte metody s názvem `MergeDisconnect`. Tyto metody zrušit propojení element z modelu, pokud je k odstranění.  
  
2.  V **DSL Explorer**vyberte nebo vytvořte sloučení direktivu Element, který chcete přizpůsobit. V **DSL podrobnosti** nastavte **používá vlastní sloučení**.  
  
     Pokud nastavíte tuto možnost **proces sloučení** a **dál sloučení** možnosti jsou ignorovány. Váš kód bude místo něj použita.  
  
3.  Znovu sestavte řešení. Bude trvat déle než obvykle, protože soubory generovaného kódu, se budou aktualizovat z modelu.  
  
     Zobrazí se chybové zprávy. Dvakrát klikněte chybové zprávy, které najdete v pokynech v generovaného kódu. Tyto pokyny vás vyzve k zadejte dvě metody, `MergeRelate` *YourDomainClass* a `MergeDisconnect` *YourDomainClass*  
  
4.  Zápis metod v definici třídu v samostatném souboru kódu. Příklady, které jste dříve prověřovány by měl naznačují, co potřebujete.  
  
 Kód vlastní sloučení nebude mít vliv na kód, který vytvoří objekty a vztahy přímo a nebude to mít vliv jiné EMDs. Chcete-li mít jistotu, že jsou bez ohledu na to, jak vytvořit element implementované další změny, zvažte zápis `AddRule` a `DeleteRule` místo. Další informace najdete v tématu [pravidla rozšíří změny v rámci modelu](../modeling/rules-propagate-changes-within-the-model.md).  
  
## <a name="redirecting-a-merge-operation"></a>Přesměrování operace sloučení  
 Direktiva dopředného sloučení přesměruje cíl operace sloučení. Nový cíl je obvykle vnoření nadřazený počáteční cíli.  
  
 V DSL, který byl vytvořen pomocí šablony diagram součásti, například porty jsou vloženy do součásti. Porty jsou zobrazeny jako malé obrazce na okraji obrazce součásti. Uživatel vytvoří porty tak, že přetáhnete nástroj Port na obrazec součásti. Ale v některých případech uživatel nastavuje nástroj Port omylem tažením na existující port, místo komponentu, a operace se nezdaří. To je snadno chybu, pokud existuje několik existující porty. Chcete-li uživatelům vyhnout této nepříjemnosti, můžete povolit porty být přetáhli existující port, ale mají akce přesměrován na komponentu nadřazené. Operaci funguje, jako kdyby cílový element komponentu.  
  
 Direktiva dopředného sloučení můžete vytvořit v řešení pro komponenty modelu. Pokud zkompilování a spuštění v původním řešení, měli byste vidět, že uživatelé můžete přetáhnout libovolný počet **vstupní Port** nebo **výstupní Port** elementy z **sada nástrojů** k **Součást** elementu. Port se však nelze přetáhnout pro existující port. Není k dispozici ukazatel je upozorní, že tento přesun není povolen. Však můžete vytvořit direktivu dopředného sloučení tak, aby port, náhodně vyřadit na existujícím **vstupní Port** předáván **součást** element.  
  
#### <a name="to-create-a-forward-merge-directive"></a>Chcete-li vytvořit direktivu dopředného sloučení  
  
1.  Vytvoření [!INCLUDE[dsl](../modeling/includes/dsl_md.md)] řešení pomocí šablony součástí modelu.  
  
2.  Zobrazení **DSL Explorer** otevřením DslDefinition.dsl.  
  
3.  V **DSL Explorer**, rozbalte položku **domény třídy**.  
  
4.  **ComponentPort** domény abstraktní třída je základní třída i **InPort** a **OutPort**. Klikněte pravým tlačítkem na **ComponentPort** a pak klikněte na **přidejte nový Element sloučení – direktiva**.  
  
     Nový **sloučení direktivu Element** uzel se objeví pod uzlem **Element sloučení direktivy** uzlu.  
  
5.  Vyberte **sloučení direktivu Element** uzlu a otevřete **DSL podrobnosti** okno.  
  
6.  Vyberte v seznamu Třída indexování **ComponentPort**.  
  
7.  Vyberte **předávat sloučení do jiné domény třídy**.  
  
8.  V seznamu pro výběr cesta rozbalte **ComponentPort**, rozbalte položku **ComponentHasPorts**a potom vyberte **součást**.  
  
     Novou cestu by se měla podobat následujícímu:  
  
     **ComponentHasPorts.Component/!Component**  
  
9. Uložte řešení a potom kliknutím na tlačítko úplně vpravo na transformace šablony **Průzkumníku řešení** panelu nástrojů.  
  
10. Sestavení a spuštění řešení. Novou instanci třídy [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] se zobrazí.  
  
11. V **Průzkumníku**, otevřete Sample.mydsl. Diagram a **ComponentLanguage nástrojů** zobrazí.  
  
12. Přetáhněte **vstupní Port** z **sada nástrojů** do jiného **vstupní Port.** V dalším kroku přetáhněte **OutputPort** k **InputPort** a pak do jiného **OutputPort**.  
  
     Není k dispozici ukazatele byste neměli vidět a nyní byste měli mít vyřadit nové **vstupní Port** na stávající. Vyberte novou **vstupní Port** a přetáhněte jej do jiného bodu **součást**.  
  
## <a name="see-also"></a>Viz také  
 [Navigace a aktualizace modelu v programovém kódu](../modeling/navigating-and-updating-a-model-in-program-code.md)   
 [Přizpůsobení nástrojů a sady nástrojů](../modeling/customizing-tools-and-the-toolbox.md)   
 [Ukázka diagramy okruh DSL](http://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)