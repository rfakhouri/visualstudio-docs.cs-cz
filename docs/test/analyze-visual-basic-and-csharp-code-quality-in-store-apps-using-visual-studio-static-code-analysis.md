---
title: "Analýza kvality kódu jazyka Visual Basic a C# v aplikacích pro UPW pomocí sady Visual Studio statickou analýzu kódu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codeanalysis.propertypages.csvb.express
ms.assetid: cab553fc-19a9-4cbf-858e-8200258ffe50
caps.latest.revision: "14"
author: erickson-doug
ms.author: douge
manager: douge
ms.openlocfilehash: e61f307872f60da316480d3654507b5225588f41
ms.sourcegitcommit: c0422a3d594ea5ae8fc03f1aee684b04f417522e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/02/2017
---
# <a name="analyze-visual-basic-and-c-code-quality-in-uwp-apps-using-visual-studio-static-code-analysis"></a>Analýza kvality kódu jazyka Visual Basic a C# v aplikacích pro UPW pomocí sady Visual Studio Statická analýza kódu
![Platí pro systém Windows a Windows Phone](../debugger/media/windows_and_phone_content.png "windows_and_phone_content")  
  
 Nástroj pro analýzu kódu v aplikaci Visual Studio Express prověří kódu pro sadu běžných defekty a porušení osvědčených postupů programování. Upozornění analýzy kódu se liší od kompilátoru chyby a upozornění, protože nástroj pro analýzu kódu hledá vzory konkrétního kódu, které jsou platné, ale stále vytvořit problémy pro vás nebo další uživatelé, kteří používají váš kód. Analýza kódu můžete také získat defekty ve vašem kódu, který je obtížné zjistit prostřednictvím testování. Spuštěný nástroj pro analýzu kódu v pravidelných intervalech během vývojových procesech můžete vylepšit kvalitu dokončené aplikace.  
  
> [!NOTE]
>  Visual Studio Ultimate, Visual Studio Premium a Visual Studio Professional můžete použít všechny funkce analýzy kódu. V tématu [analýza kvality aplikace pomocí nástrojů pro analýzu kódu](http://msdn.microsoft.com/library/dd264897.aspx) v knihovně MSDN.  
  
## <a name="in-this-topic"></a>V tomto tématu  
 Se dozvíte:  
  
 [Spuštění analýzy kódu](../test/analyze-visual-basic-and-csharp-code-quality-in-store-apps-using-visual-studio-static-code-analysis.md#BKMK_Run)  
  
 [Analýza a řešení upozornění analýzy kódu](../test/analyze-visual-basic-and-csharp-code-quality-in-store-apps-using-visual-studio-static-code-analysis.md#BKMK_Analyze)  
  
 [Potlačení upozornění analýzy kódu](../test/analyze-visual-basic-and-csharp-code-quality-in-store-apps-using-visual-studio-static-code-analysis.md#BKMK_Suppress)  
  
 [Vyhledávání a filtrování výsledků analýzy kódu](../test/analyze-visual-basic-and-csharp-code-quality-in-store-apps-using-visual-studio-static-code-analysis.md#BKMK_Search)  
  
 [Upozornění analýzy kódu pro Visual Basic a C#](../test/analyze-visual-basic-and-csharp-code-quality-in-store-apps-using-visual-studio-static-code-analysis.md#BKMK_Warnings)  
  
##  <a name="BKMK_Run"></a>Spuštění analýzy kódu  
 Spuštění analýzy kódu pro řešení sady Visual Studio:  
  
-   Na **sestavení** nabídce zvolte **spustit analýza kódu v řešení**.  
  
 Pokud chcete automaticky spustit analýza kódu pokaždé, když vytváříte projekt:  
  
1.  Klikněte pravým tlačítkem na název projektu v Průzkumníku řešení a potom zvolte **vlastnosti**.  
  
2.  Na stránce vlastností projektu zvolte **analýza kódu** a potom zvolte **povolit analýza kódu v sestavení (definuje CODEANALYSIS konstanta)**.  
  
 Kompiluje řešení a analýza kódu spustí. Výsledky se zobrazí v okně nástroje Analýza kódu.  
  
 ![Analýza kódu – okno](../test/media/ca_managed_collapsed.png "CA_Managed_Collapsed")  
  
##  <a name="BKMK_Analyze"></a>Analýza a řešení upozornění analýzy kódu  
 K analýze konkrétní upozornění, klikněte na název upozornění v okně nástroje Analýza kódu. Toto upozornění se rozbalí a zobrazí podrobné informace o problému.  
  
 ![Upozornění analýzy kódu rozšířit](../test/media/ca_managed_callouts.png "CA_Managed_Callouts")  
  
 Pokud rozbalíte upozornění, řádek kódu, který způsobil upozornění zvýrazněn v editoru kódu v sadě Visual Studio.  
  
 ![Code analysis zvýraznění textu](../test/media/ca_managed_sourceline.png "CA_Managed_SourceLine")  
  
 Po zjištění problému, abyste ho mohli vyřešit ve vašem kódu. Poté znovu spusťte analýza kódu a ujistěte se, že upozornění již nadále nebude zobrazovat v okně nástroje Analýza kódu a není má vaše oprava vyvolá nové upozornění.  
  
> [!TIP]
>  Analýza kódu z okna Analýza kódu můžete znovu spustit. Klikněte **analyzovat** tlačítko a zvolte oboru analýzy. Můžete znovu spustit analýzu na celé řešení nebo na vybrané projektu.  
  
##  <a name="BKMK_Suppress"></a>Potlačení upozornění analýzy kódu  
 Existují situace, kdy můžete rozhodnout není opravte upozornění analýzy kódu. Můžete se rozhodnout řešení upozornění vyžaduje příliš mnoho Změna kódu ve vztahu k pravděpodobnost, že problém vyvstanou v jakékoli reálného provádění kódu. Nebo možná se domníváte, že není vhodný pro konkrétní kontext analýzy, který se používá v upozornění. Jednotlivé upozornění můžete potlačit tak, aby se nebude zobrazovat v okně nástroje Analýza kódu.  
  
 Potlačit upozornění:  
  
1.  Pokud podrobné informace se nezobrazí, klikněte na název upozornění rozbalte ho.  
  
2.  Vyberte **akce** odkaz v dolní části upozornění.  
  
3.  Přejděte na příkaz **potlačit zpráva** a potom vyberte buď **zdroje v** nebo **v souboru potlačení**.  
  
    -   **Ve zdroji** vloží `SuppressMessage` atribut ve zdrojovém souboru výše metodu, která generuje upozornění. Díky tomu potlačení zjistitelná.  
  
    -   **V souboru potlačení** přidá `SuppressMessage` atribut **GlobalSuppressions.cs** souboru projektu. To může zjednodušit správu suppressions. Všimněte si, že `SuppressMessage` přidány do atribut **GlobalSuppression.cs** také cílí na metodu, která generuje upozornění. Neskrývá upozornění globálně.  
  
     Vaše rozhodnutí, jestli se má potlačit upozornění na zdrojový soubor nebo v souboru potlačení závisí na vaší kódování stylu a potřebách.  
  
##  <a name="BKMK_Search"></a>Vyhledávání a filtrování výsledků analýzy kódu  
 Můžete hledat dlouhými seznamy zprávy upozornění a můžete filtrovat upozornění v řešení vícenásobného projektu.  
  
 ![Hledání a filtrování okno analýzy kódu](../test/media/ca_searchfilter.png "CA_SearchFilter")  
  
 V [!INCLUDE[vs_dev11_expwin_long](../misc/includes/vs_dev11_expwin_long_md.md)], všechny code analysis upozornění mají úroveň závažnosti upozornění.  
  
##  <a name="BKMK_Warnings"></a>Upozornění analýzy kódu pro Visual Basic a C#  
 Analýza kódu vyvolá následující upozornění:  
  
 [CA1001: Typy, které vlastní uvolnitelné pole by měly být uvolnitelné](http://msdn.microsoft.com/library/ms182172.aspx)  
  
 [CA1821: Odstraňte prázdné finalizační metody](http://msdn.microsoft.com/library/bb264476.aspx)  
  
 [CA2213: Uvolnitelné pole by měl zlikvidován.](http://msdn.microsoft.com/library/ms182328.aspx)  
  
 [CA2229: Implementovat Serializační konstruktory](http://msdn.microsoft.com/library/ms182343.aspx)  
  
 [CA2231: Přetižte operátor equals při přepsání ValueType.Equals](http://msdn.microsoft.com/library/ms182359.aspx)
