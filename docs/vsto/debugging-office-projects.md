---
title: "Ladění projektů Office | Microsoft Docs"
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
- Excel projects [Office development in Visual Studio], debugging
- Word projects [Office development in Visual Studio], debugging
- Outlook [Office development in Visual Studio], debugging
- debugging [Office development in Visual Studio], Outlook projects
- Office projects [Office development in Visual Studio], debugging
- Outlook [Office development in Visual Studio], projects
ms.assetid: e360b9e9-9f36-48f0-a0c5-a6980fb47a87
caps.latest.revision: "52"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 110d6231da40ab59c3979b97441b3ac0ad458b3e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="debugging-office-projects"></a>Ladění projektů Office
  Projekty Office můžete ladit pomocí stejné Microsoft [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] nástrojů, které můžete používat pro jiné [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projekty. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]Funkce, jako je například možnost Vložit zarážky a zobrazit proměnné v ladicího programu **místní hodnoty –** okno, jsou také k dispozici při ladění projektů Office. Další informace o [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] nástroje pro ladění, najdete v části [ladění v sadě Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).  
  
> [!TIP]  
>  Ke zjednodušení, ladění, zavřete všechny otevřené instance aplikace Office, než sestavení a ladění.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
> [!NOTE]  
>  Máte zájem o vývoji řešení, které rozšiřují Office prostředí napříč [více platforem](https://dev.office.com/add-in-availability)? Podívejte se na [Office Add in modelu](https://dev.office.com/docs/add-ins/overview/office-add-ins). Doplňky Office mají malé nároky ve srovnání s doplňků VSTO a řešení a můžete je vytvořit pomocí téměř jakoukoli webové programování technologie, jako je například HTML5, JavaScript, CSS3 a XML.  
  
## <a name="starting-and-stopping-the-debugger"></a>Spuštění a zastavení ladicího programu  
 Můžete spustit ladění projektu aplikace Office, stejně jako spuštění ladění dalších [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] projekty; například můžete stisknutím klávesy F5. Při spuštění ladění projektu doplňku VSTO spuštěn nový proces pro cílové aplikace Office a že je načtený doplňku VSTO.  
  
 Při spuštění ladění projektu úrovni dokumentu se otevře v nový proces Word či Excel dokumentu nebo sešitu.  
  
 Po zastavení ladicího programu ladicí program ukončit proces aplikace náhle nebo odpojí, pokud máte ladicí program nastavit odpojit. Všechny dokumenty, které jsou otevřeny v procesu ukončenou aplikace Office jsou také uzavřena bez upozornění a veškeré neuložené změny budou ztraceny. To může zahrnovat všechny dokumenty nebo sešity, které jsou otevřené spuštěného ladicího programu.  
  
 Obvykle je lepší odpojení od proces před zastavením ladicího programu, takže můžete ukončit aplikaci Office běžným způsobem. Je možné odebrat z procesu nejprve Pokud chcete pracovat s otevřít dokument nebo listu po zastavení ladicího programu.  
  
 Pokud ladíte přizpůsobení na úrovni dokumentu ve Wordu, opakovaně zastavení ladicího programu a způsobí ukončení najednou aplikace Word může vést k normální šablony poškození. Pokud k tomu dojde, můžete odstranit poškozená normální šablony a jej bude automaticky znovu vytvořen při příštím otevření aplikace Word. Však nejsou vytvořeny žádné makra, které byly uloženy v šabloně Normální.  
  
### <a name="debug-office-2013-vsto-add-ins-by-using-either-office-2013-or-office-2016"></a>Ladění Office 2013 VSTO doplňků pomocí Office 2013 nebo Office 2016  
 Pokud používáte Visual Studio 2015 a budete mít obě verze Office nainstalován-souběžného, spustí se v sadě Visual Studio Office 2016. Pokud používáte Visual Studio 2013, Visual Studio spustí Office 2013.  
  
 Pokud chcete ladit vaše doplňku VSTO v jiné verzi systému Office (2013 nebo 2016), otevřete **Návrhář projektu**a v **ladění** , zvolte **počáteční vnějšímu programu**tlačítko. Pak přejděte do umístění spustitelného souboru příslušné aplikace Office.  
  
## <a name="f10-and-f11-behavior"></a>F10 a F11 chování  
 Při spuštění ladění projektu Office F10 a F11 nemají stejné chování jako při spuštění ladění další projekty Visual Basic a C#. V projektech Visual Basic a C# zastaví ladicího programu na hlavní funkce; v projektech Office Visual Studio nemá kontrolu nad hlavní funkce aplikace Office. Ale během ladění, F10 a F11 mají stejné funkce jako projekty Visual Basic a C#.  
  
## <a name="displaying-exceptions"></a>Zobrazení výjimky  
 Kvůli způsobu, jakým spravovaný kód a komunikuje s nespravovaným kódem, Visual Studio nezobrazuje chyb, které jsou vyvolány pomocí aplikace Microsoft Office. Například pokud VSTO doplňku vytvořili pomocí nástroje pro vývoj pro Office v sadě Visual Studio vyvolá výjimku, aplikace Microsoft Office bude pokračovat bez zobrazení k chybě. Pokud chcete zobrazit tyto chyby, nastavte ladicí program na přerušení na výjimky modulu CLR. Další informace najdete v tématu [Správa výjimek pomocí ladicího programu](/visualstudio/debugger/managing-exceptions-with-the-debugger).  
  
 Pokud jste nastavili ladicí program na přerušení na výjimky modulu CLR, všechny výjimky teď rozdělit ladicího programu, včetně šablony, které mají zpracovávat a některé first chance výjimky z modulu runtime sebe, což nemusí být relevantní pro váš projekt. Chyby, která odkazuje na msosec není byl nalezen se zobrazí v každém projektu, ale jsou bezpečně ignorovat. Tyto výjimky msosec nebude mít vliv na vaše řešení.  
  
 Můžete také použít **zkuste... Catch –** příkazy kolem vaše metody zachycení výjimky.  
  
 Ve výchozím nastavení Visual Studio také nemá zobrazení pouze v době chyby ladění pro projekty Office; Tuto funkci však můžete povolit, aby se zobrazí chyby, které jsou vyvolány. Další informace najdete v tématu [ladění JIT v sadě Visual Studio](/visualstudio/debugger/just-in-time-debugging-in-visual-studio).  
  
## <a name="command-line-arguments"></a>Argumenty příkazového řádku.  
 Pokud **spustit akci** na **ladění** stránka vlastností nastavena na **spustit projekt**, Visual Studio nepoužívá argumenty příkazového řádku při ladění projektu, i když máte Zadaný argumenty příkazového řádku, jako možnosti spuštění. Pokud chcete použít argumenty příkazového řádku při spuštění ladění, je nutné vybrat **spustit akci** jiné než **spustit projekt**.  
  
## <a name="source-control"></a>Správa zdrojového kódu  
 Ladění vlastnosti nejsou sdílí několik uživatelů v rámci správy zdrojového kódu. Projekty Visual Basic a C# uložit ladění vlastnosti v souboru konkrétního uživatele (*ProjectName*. vbproj.user nebo *ProjectName*. csproj.user), a tento soubor není ve správě zdrojového kódu. Pokud je ladění víc než jedna osoba, každou osobu, musíte zadat vlastnosti ladění ručně.  
  
## <a name="debugging-cached-datasets-in-a-document-level-project"></a>Ladění datové sady v mezipaměti v projektech na úrovni dokumentu  
 Pokaždé, když vytváříte projekt, je datová sada vyprázdnit a znovu vytvoří. Pokud chcete ladit datové sady v mezipaměti, musíte otevřít dokument mimo Visual Studio a pak připojit ladicí program.  
  
## <a name="debugging-word-document-projects-based-on-the-word-97-2003-document-doc-format"></a>Ladění projektů dokument aplikace Word podle dokument aplikace Word 97-2003 (* .doc) formátu  
 K ladění projektu dokument aplikace Word na základě dokumentu Word 97-2003 (* .doc) formátu, je nutné přidat do seznamu důvěryhodných složky složce projektu. Další informace o tom, jak to udělat najdete v tématu [udělení vztah důvěryhodnosti s dokumenty](../vsto/granting-trust-to-documents.md)...  
  
## <a name="debugging-disabled-add-ins"></a>Ladění zakázané doplňky  
 Aplikace Microsoft Office můžete zakázat doplňků VSTO které neočekávanému chování. Aplikace Microsoft Office zakáže doplňků VSTO zabránit problematické kód načítání při každém spuštění aplikace. Také je však snadno způsobit neočekávané chování během typické ladění. Informace o tom, jak znovu povolit doplňků VSTO najdete v tématu [postupy: opětovné povolení VSTO Add-in, má bylo zakázáno](../vsto/how-to-re-enable-a-vsto-add-in-that-has-been-disabled.md).  
  
 Existují dva typy zakázání, že aplikace Microsoft Office používat pro doplňky VSTO: pevné zakázání a logicky zakázání.  
  
### <a name="hard-disabling"></a>Zakázání pevný  
 Zakázání pevného může dojít, když doplňku VSTO způsobí, že aplikace neočekávaně ukončena. Ho může také dojít k ve svém vývojovém počítači zastavení ladicího programu při <xref:Microsoft.Office.Tools.AddIn.Startup> spouští obslužné rutiny událostí v doplňku VSTO. Pokud doplňku VSTO je pevný zakázáno, zobrazí se v **zakázané položky** seznamu v aplikaci.  
  
 Pokud aplikace Office pevný zakáže VSTO doplňku vytvořili pomocí nástroje pro vývoj pro Office v sadě Visual Studio, aplikace zakáže pouze VSTO doplněk způsobující selhání. Jiné doplňků VSTO vytvořili pomocí nástroje pro vývoj pro Office v sadě Visual Studio pro příslušnou aplikaci Office, budou i nadále načíst.  
  
### <a name="soft-disabling"></a>Logicky zakázání  
 Logicky zakázání může dojít, když doplňku VSTO vytvoří chybu, který nevyvolá aplikace neočekávaně zavřete. Například aplikace může soft zakázat doplňků VSTO v případě, že nastane neošetřenou výjimku při <xref:Microsoft.Office.Tools.AddIn.Startup> spouští obslužné rutiny události. Pokud doplňku VSTO je logicky zakázáno, zobrazí se v **neaktivní aplikace doplňky** v aplikaci a aplikace v seznamu změní hodnotu **LoadBehavior –** položky registru pro VSTO Doplněk to znamená, že je odpojen. Další informace o **LoadBehavior** položky registru najdete v části [položky registru pro doplňky VSTO](../vsto/registry-entries-for-vsto-add-ins.md).  
  
## <a name="troubleshooting-installation-errors-by-using-the-event-viewer"></a>Řešení potíží s chybami instalace pomocí prohlížeče událostí  
 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Zapíše zprávy do prohlížeče událostí v systému Windows pro všechny výjimky, které se vyvolá, když si nainstalujete nebo odinstalujete řešení pro systém Office. Tyto zprávy můžete použít k vyřešení instalace a nasazení problémy.  
  
## <a name="troubleshooting-startup-errors-by-using-a-log-file-and-error-messages"></a>Řešení potíží s chybami spuštění pomocí souboru protokolu a chybové zprávy  
 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Můžete zapsat všechny chyby, ke kterým došlo během spouštění protokolu soubor nebo zobrazit jednotlivé chyby v okně se zprávou. Tyto možnosti jsou ve výchozím nastavení vypnuté. Možnosti můžete zapnout, vytváření proměnných prostředí.  
  
 Chcete-li zobrazit jednotlivé chyby v okně se zprávou, vytvořit proměnnou prostředí s názvem `VSTO_SUPPRESSDISPLAYALERTS` a nastavte ji na 0 (nula). Zprávy můžete potlačit tím odstraňování proměnné prostředí nebo jeho nastavení na hodnotu 1 (jedna).  
  
 Zapsat chyby do souboru protokolu, vytvořit proměnnou prostředí s názvem `VSTO_LOGALERTS` a nastavte ji na hodnotu 1 (jedna). [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] Vytváří protokolový soubor ve složce, která obsahuje manifest nasazení pro doplňku VSTO nebo ve složce, která obsahuje dokument nebo sešitu, která souvisí s úpravami. Pokud to nepomůže, [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] vytváří protokolový soubor ve složce místní % TEMP %. Pro aplikační úrovni doplňků VSTO, výchozí název je *název doplňku*. vsto.log. Projekty na úrovni dokumentu, je název souboru protokolu *název dokumentu*. *rozšíření*.log, jako je například ExcelWorkbook1.xlsx.log. K zastavení protokolování chyb, odstraňte proměnnou prostředí nebo ji nastavte na hodnotu 0 (nula).  
  
## <a name="see-also"></a>Viz také  
 [Vytváření řešení pro systém Office](../vsto/building-office-solutions.md)   
 [Postupy: opětovné povolení doplňku VSTO, který byl zakázán](../vsto/how-to-re-enable-a-vsto-add-in-that-has-been-disabled.md)   
 [Programování doplňků VSTO](../vsto/programming-vsto-add-ins.md)  
  
  