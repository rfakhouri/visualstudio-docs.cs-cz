---
title: "Architektura přizpůsobení na úrovni dokumentu | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- VSTOLoader.dll
- formats [Office development in Visual Studio]
- file formats [Office development in Visual Studio]
- vstoee.dll
- managed code extensions [Office development in Visual Studio], definition
- document-level customizations [Office development in Visual Studio]
- AddInLoader.dll
- architecture [Office development in Visual Studio], document-level customizations
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 09a8700086ec8a718e14764f807e57fcb1f882f7
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/10/2018
---
# <a name="architecture-of-document-level-customizations"></a>Architektura přizpůsobení na úrovni dokumentu
  [!INCLUDE[vs_dev12](../vsto/includes/vs-dev12-md.md)]zahrnuje projekty pro vytvoření úpravy na úrovni dokumentů pro Microsoft Office Word a Microsoft Office Excel. Toto téma popisuje následující aspektů přizpůsobení na úrovni dokumentu:  
  
-   [Principy přizpůsobení](#UnderstandingCustomizations)  
  
-   [Součásti přizpůsobení](#Components)  
  
-   [Jak fungují přizpůsobení pomocí aplikace Microsoft Office](#HowCustomizationsWork)  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Obecné informace o vytváření úpravy na úrovni dokumentů najdete v tématu [přehled vývoje řešení pro systém Office &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md), [Začínáme programování přizpůsobení na úrovni dokumentu ve Wordu](../vsto/getting-started-programming-document-level-customizations-for-word.md), a [Začínáme s programováním přizpůsobení na úrovni dokumentu pro Excel](../vsto/getting-started-programming-document-level-customizations-for-excel.md).  
  
##  <a name="UnderstandingCustomizations"></a>Principy přizpůsobení  
 Když používáte Office developer tools v sadě Visual Studio k vytvoření přizpůsobení na úrovni dokumentu, můžete vytvořit sestavení spravovaného kódu, který je přidružen konkrétní dokumentu. Dokument nebo sešitu s propojené sestavení se říká, že jste nahráli rozšíření kódu. Další informace najdete v tématu [návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md).  
  
 Když uživatel otevře dokument, je načíst sestavení v aplikaci Microsoft Office. Po načíst sestavení přizpůsobení můžete reakce na události dokumentu je otevřen. Přizpůsobení můžete také volání do modelu objektu automatizovat a rozšířit aplikace, když je otevřený v dokumentu, a může použít jakékoli třídy v [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)].  
  
 Sestavení komunikuje s komponentami aplikace modelu COM pomocí primární spolupracující sestavení aplikace. Další informace najdete v tématu [primární zprostředkovatel komunikace s objekty sestavení sady Office](../vsto/office-primary-interop-assemblies.md) a [přehled vývoje řešení pro systém Office &#40; VSTO &#41; ](../vsto/office-solutions-development-overview-vsto.md).  
  
 Pokud uživatel otevře více přizpůsobení na úrovni dokumentu ve stejnou dobu, je v doméně jinou aplikaci načíst každé sestavení. To znamená, že jedno řešení, které se chová nesprávně nemohou způsobit jiných řešení selhání. Úpravy na úrovni dokumentů jsou navrženy pro práci s jedním dokumentem v jediné doméně aplikace. Nejsou určeny pro komunikaci mezi dokumenty. Další informace o doménách aplikací najdete v tématu [aplikační domény](/dotnet/framework/app-domains/application-domains).  
  
> [!NOTE]  
>  Úpravy na úrovni dokumentů, které vytvoříte pomocí doplňku Office developer tools v sadě Visual Studio jsou určeny k použití jenom v případě, že se koncový uživatel spustí aplikaci. Pokud je aplikace spuštěna prostřednictvím kódu programu, například pomocí automatizace, přizpůsobení nemusí fungovat podle očekávání.  
  
### <a name="design-time-and-run-time-experiences"></a>Návrh a běhové prostředí  
 Zjistit architektura přizpůsobení na úrovni dokumentu pomáhá pochopit možnosti návrhu řešení a spuštění řešení.  
  
#### <a name="design-time"></a>V době návrhu  
 Možnosti návrhu zahrnuje následující kroky:  
  
1.  Vývojář vytvoří projektu úrovni dokumentu v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Projekt obsahuje dokument a sestavení, který se spouští za dokumentu. Dokument možná již existuje (pravděpodobně vytvořena návrhářem) nebo společně s projektu lze vytvořit nový dokument.  
  
2.  Návrhář – buď vývojář, který vytvoří projekt nebo někdo jiný – vytvoří konečnou vzhledu a chování dokumentu pro koncového uživatele.  
  
#### <a name="run-time"></a>Čas spuštění  
 Běhové prostředí zahrnuje následující kroky:  
  
1.  Koncový uživatel otevře dokument nebo sešit, který se má spravovat rozšíření kódu.  
  
2.  Tento dokument nebo sešit načte kompilované sestavení.  
  
3.  Sestavení odpoví na události, protože uživatel pracuje v dokumentu nebo sešitu.  
  
#### <a name="developer-and-end-user-perspective-compared"></a>Pro vývojáře a porovnání perspektivy koncového uživatele  
 Protože vývojáři funguje hlavně v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]a koncový uživatel pracuje v Word či Excel, existují dva způsoby pochopení úpravy na úrovni dokumentů.  
  
|Pro vývojáře perspektivy|Perspektivy koncového uživatele|  
|-----------------------------|----------------------------|  
|Pomocí [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], vývojář zapíše kód, který je přístupný pro Word a Excel.<br /><br /> I když se může zdát, že vývojář vytváří spustitelný soubor, který spouští Word či Excel, probíhá proces ve skutečnosti opačným způsobem. Dokument je přiřazena k sestavení a ukazatel na toto sestavení obsahuje. Po otevření dokumentu Word či Excel vyhledá sestavení a spustí kód v reakci na všechny zpracovávaný události.|Ty, kteří používají řešení jednoduše otevřít dokument nebo sešit (nebo vytvořit nový dokument ze šablony) stejným způsobem jako neotevřou by jakýkoli jiný soubor aplikace Microsoft Office.<br /><br /> Sestavení poskytuje přizpůsobení v dokumentu nebo sešitu, jako je například automaticky vyplní s aktuální data, nebo zobrazuje dialogové k požadavku na informace.|  
  
### <a name="supported-document-formats-for-document-level-customizations"></a>Podporované formáty dokumentů pro úpravy na úrovni dokumentů  
 Když vytvoříte vlastní nastavení projektu, můžete formát dokumentu, který chcete použít v projektu. Další informace najdete v tématu [postupy: vytváření projektů Office v sadě Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md).  
  
 Následující tabulka uvádí formáty dokumentů, které můžete použít v přizpůsobeních na úrovni dokumentu pro Excel a Word.  
  
|Excel|Word|  
|-----------|----------|  
|Sešit aplikace Excel (XLSX)<br /><br /> Sešit aplikace Excel s podporou maker (.xlsm)<br /><br /> Binární sešit aplikace Excel (XLSB)<br /><br /> Sešit aplikace Excel 97-2003 (XLS)<br /><br /> Šablony aplikace Excel (XLTX)<br /><br /> Šablona s podporou maker (XLTM) v aplikaci Excel<br /><br /> Šablony aplikace Excel 97-2003 (XLT)|Dokument aplikace Word (.docx)<br /><br /> Dokument aplikace Word s podporou maker (DOCM)<br /><br /> Dokument aplikace Word 97-2003 (DOC)<br /><br /> Šablony aplikace Word (dotx)<br /><br /> Šablony aplikace Word s podporou maker (dotm)<br /><br /> Šablony aplikace Word 97-2003 (dot)|  
  
 Měli byste navrhnout rozšíření spravovaného kódu pouze pro dokumenty v podporovaném formátu. Určité události, jinak hodnota nemusí vyvolá, když dokument se otevře v aplikaci. Například <xref:Microsoft.Office.Tools.Excel.Workbook.Open> událost se vyvolá, když používáte rozšíření spravovaného kódu se sešity, které jsou uloženy v tabulkovém formátu XML aplikace Excel nebo ve formátu webové stránky (*.htm; .html).  
  
### <a name="support-for-word-documents-that-have-xml-file-name-extensions"></a>Podpora pro dokumenty aplikace Word, které mají přípony názvů souborů .xml  
 Šablony projektu na úrovni dokumentu Nepovolit vytváření projektů podle následující formáty souborů:  
  
-   Dokument aplikace Word XML (* xml).  
  
-   Dokument aplikace Word 2003 XML (* xml).  
  
 Pokud chcete, aby vaši koncoví uživatelé používat vlastní nastavení v těchto formátů souboru, vytvořit a nasadit vlastní nastavení, která používá jednu z podporovaných formátů, zadaný v předchozí tabulce. Po instalaci přizpůsobení, koncoví uživatelé mohou uložte dokument do Wordového dokumentu XML (* xml) formátu nebo dokument aplikace Word 2003 XML (\*xml) formát a přizpůsobení budou nadále fungovat podle očekávání.  
  
##  <a name="Components"></a>Součásti přizpůsobení  
 Hlavní součástí přizpůsobení jsou dokumentu a sestavení. Kromě těchto součástí existuje několik dalších částí, které hraje důležitou roli v tom, jak aplikace Microsoft Office zjišťovat a načíst přizpůsobení.  
  
### <a name="deployment-manifest-and-application-manifest"></a>Manifest nasazení a Manifest aplikace  
 Přizpůsobení používat k identifikaci a načíst nejnovější verze sestavení přizpůsobení manifestů aplikace a manifesty nasazení. Nasazení manifest odkazuje na aktuální manifest aplikace. Aplikace manifest odkazuje na sestavení přizpůsobení a určuje vstupní bod – třída (nebo třídy) provést v sestavení. Další informace najdete v tématu [aplikace a manifesty nasazení v řešeních pro systém Office](../vsto/application-and-deployment-manifests-in-office-solutions.md).  
  
### <a name="visual-studio-tools-for-office-runtime"></a>Visual Studio Tools for Office Runtime  
 Pokud chcete spustit úpravy na úrovni dokumentů, které jsou vytvořené pomocí doplňku Office developer tools v sadě Visual Studio, musí mít počítače koncového uživatele [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] nainstalována. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Obsahuje nespravované součásti, které zatížení přizpůsobení sestavení a sadu spravovaných sestavení. Tyto spravované sestavení poskytují objektový model, který používá váš kód přizpůsobení automatizovat a rozšířit hostitelskou aplikaci.  
  
 Další informace najdete v tématu [Visual Studio Tools for Office Runtime přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
##  <a name="HowCustomizationsWork"></a>Jak fungují přizpůsobení pomocí aplikace Microsoft Office  
 Když uživatel otevře dokument, který je součástí přizpůsobení aplikace Microsoft Office, aplikace použije manifestu nasazení, který k dokumentu pro vyhledání a načtení nejaktuálnější verzi sestavení vlastní nastavení. V dokumentu vlastní vlastnost s názvem _AssemblyLocation je uloženo umístění manifestu nasazení. Řetězec, který identifikuje toto umístění se vloží do vlastnost při sestavování řešení.  
  
 Nasazení manifestu body do manifestu aplikace, které pak odkazuje na nejnovější sestavení. Další informace najdete v tématu [aplikace a manifesty nasazení v řešeních pro systém Office](../vsto/application-and-deployment-manifests-in-office-solutions.md).  
  
 Následující obrázek znázorňuje základní architektura přizpůsobení na úrovni dokumentu.  
  
 ![Architektura přizpůsobení office 2007](../vsto/media/office07-custom.png "architektura přizpůsobení Office 2007")  
  
> [!NOTE]  
>  V řešení pro systém Office cílených [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)], řešení volání do modelu objektu hostitelské aplikace podle pomocí informací o typu primární spolupracující sestavení (PIA), vložené v sestavení řešení, namísto volání do primární přímo. Další informace najdete v tématu [návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md).  
  
### <a name="loading-process"></a>Proces načítání  
 Následující kroky nastane, když uživatel otevře dokument, který je součástí řešení Microsoft Office.  
  
1.  Aplikace Microsoft Office kontroluje vlastnosti vlastní šablony dokumentů a zjistěte, zda jsou rozšíření spravovaného kódu, které jsou přidružené k dokumentu. Další informace najdete v tématu [přehled vlastností dokumentu vlastní](../vsto/custom-document-properties-overview.md).  
  
2.  Pokud je rozšíření spravovaného kódu, načtení aplikace VSTOEE.dll, který načte VSTOLoader.dll. Toto nespravované knihovny DLL, které jsou součástí zavaděč pro Visual Studio 2010 Tools for Office Runtime. Další informace najdete v tématu [Visual Studio Tools for Office Runtime přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md).  
  
3.  Načte VSTOLoader.dll [!INCLUDE[dnprdnshort](../sharepoint/includes/dnprdnshort-md.md)] a spustí spravovaná část [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)].  
  
4.  Pokud otevření dokumentu z umístění než místní počítač, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] ověřuje, zda je v umístění dokumentu **důvěryhodné umístění** v seznamu **nastavení Centra zabezpečení** pro konkrétní aplikaci Office. Pokud umístění dokumentu není v důvěryhodném umístění, přizpůsobení není důvěryhodný a zastaví proces načítání sem.  
  
5.  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Nainstaluje řešení, pokud dosud nebyl nainstalován, stáhne nejnovější manifestů aplikace a nasazení a provádí řadu kontrol zabezpečení. Další informace najdete v tématu [zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md).  
  
6.  Pokud přizpůsobení je důvěryhodný pro spuštění [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] používá ke kontrole aktualizací sestavení – manifest nasazení a manifest aplikace. Pokud je k dispozici nová verze sestavení, modul runtime stáhne novou verzi sestavení do [!INCLUDE[ndptecclick](../vsto/includes/ndptecclick-md.md)] mezipaměti na klientském počítači. Další informace najdete v tématu [nasazení řešení Office](../vsto/deploying-an-office-solution.md).  
  
7.  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Vytvoří novou doménu aplikace, ve kterém se načíst sestavení vlastní nastavení.  
  
8.  [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Načte přizpůsobení sestavení do domény aplikace.  
  
9. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Volání **spuštění** obslužné rutině událostí ve vaší vlastní nastavení sestavení. Další informace najdete v tématu [události v projektech pro systém Office](../vsto/events-in-office-projects.md)  
  
## <a name="see-also"></a>Viz také  
 [Architektura řešení pro systém Office v sadě Visual Studio](../vsto/architecture-of-office-solutions-in-visual-studio.md)   
 [Architektura doplňků VSTO](../vsto/architecture-of-vsto-add-ins.md)   
 [Visual Studio Tools for Office Runtime – přehled](../vsto/visual-studio-tools-for-office-runtime-overview.md)   
 [Zabezpečení řešení pro systém Office](../vsto/securing-office-solutions.md)   
 [Návrh a vytváření řešení pro systém Office](../vsto/designing-and-creating-office-solutions.md)   
 [Přehled přizpůsobených vlastností dokumentu](../vsto/custom-document-properties-overview.md)   
 [Data uložená v mezipaměti v přizpůsobeních na úrovni dokumentu](../vsto/cached-data-in-document-level-customizations.md)  
  
  