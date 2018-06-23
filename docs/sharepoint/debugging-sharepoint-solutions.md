---
title: Ladění řešení služby SharePoint | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.Project.WebConfigModificationDialog
- VS.SharePointTools.Project.DebuggingNotEnabled
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, debugging
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 99d7f5e813e3ac33b327ed0c2962b150b6eed755
ms.sourcegitcommit: e6b13898cfbd89449f786c2e8f3e3e7377afcf25
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/22/2018
ms.locfileid: "36327164"
---
# <a name="debug-sharepoint-solutions"></a>Ladění řešení služby SharePoint
  Můžete ladění řešení služby SharePoint pomocí [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ladicí program. Při spuštění ladění, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] na serveru SharePoint nasadí soubory projektu a pak otevře instanci web služby SharePoint ve webovém prohlížeči. Následující části popisují postup ladění aplikací služby SharePoint [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)].  
  
-   [Povolení ladění](#EnableDebug)  
  
-   [F5 ladění a proces nasazení](#Deployment)  
  
-   [Funkce projektu služby SharePoint](#Features)  
  
-   [Ladění pracovních postupů](#Workflow)  
  
-   [Ladění přijímačů událostí funkce](#FeatureEvents)  
  
-   [Povolení Rozšířené ladicí informace](#EnhancedDebug)  
  
## <a name="enable-debugging"></a>Povolení ladění
 Při první ladění řešení služby SharePoint v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], dialogové okno vás upozorní, že pokud chcete povolit ladění není nakonfigurován v souboru web.config. (V souboru web.config se vytvoří při instalaci serveru SharePoint. Další informace najdete v tématu [práce se soubory Web.config](http://go.microsoft.com/fwlink/?LinkID=149266).) Dialogové okno vám dává možnost buď spuštění projektu bez ladění nebo úprava souboru web.config. Pokud chcete povolit ladění. Pokud zvolíte možnost první, projekt se spustí normálně. Pokud si zvolíte druhou možnost, v souboru web.config nastaven tak, aby:  
  
-   Zapnout v zásobníku volání (`CallStack="true"`)  
  
-   Zakázat vlastní chyby v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] (`<customErrors mode="Off" />`)  
  
-   Povolit ladění kompilace (`<compilation debug="true">`)  
  
 Výsledný soubor web.config takto:  
  
```xml  
<?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <configuration>  
        ...  
        <SharePoint>  
            <SafeMode MaxControls="200"  
                CallStack="true"  
                DirectFileDependencies="10"  
                TotalFileDependencies="50"  
                AllowPageLevelTrace="false">  
                ...  
            </SafeMode>  
        ...  
        </SharePoint>  
        <system.web>  
            ...  
            <customErrors mode="Off" />  
            ...  
            <compilation debug="true">  
            ...  
            </compilation>  
            ...  
        </system.web>  
        ...  
    </configuration>  
```  
  
 Chcete-li změny a zakázat ladění, změňte následující [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] v souboru web.config:  
  
-   Vypnout zásobníku volání (`CallStack="false"`)  
  
-   Povolit vlastní chyby v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] (`<customErrors mode="On" />`)  
  
-   Zakázat ladění kompilace (`<compilation debug="false">`)  
  
## <a name="f5-debug-and-deployment-process"></a>Proces nasazení a ladění F5
 Při spuštění v režimu ladění projektu služby SharePoint, procesu nasazení služby SharePoint provádí následující úlohy:  
  
1.  Spouští přizpůsobitelné příkazy před nasazením.  
  
2.  Vytvoří soubor webového řešení balíčku (WSP) pomocí [!INCLUDE[vstecmsbuild](../sharepoint/includes/vstecmsbuild-md.md)] příkazy. Soubor WSP zahrnuje všechny potřebné soubory a funkce. Další informace najdete v tématu [přehled řešení](http://go.microsoft.com/fwlink/?LinkID=128154).  
  
3.  Je-li řešení služby SharePoint je řešení farmy, recyklování [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] fond aplikací pro zadaný web [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)]. Tento krok uvolní soubory uzamčený [!INCLUDE[TLA2#tla_iis5](../sharepoint/includes/tla2sharptla-iis5-md.md)] pracovní proces.  
  
4.  Pokud předchozí verze balíčku již existuje, odvolá předchozí verze funkce a souborů v souboru WSP. Tento krok deaktivuje funkcí, odinstaluje balíček řešení a poté se odstraní balíčku řešení na serveru SharePoint.  
  
5.  Nainstaluje aktuální verze funkce a souborů v souboru WSP. Tento krok přidává a nainstaluje řešení na serveru SharePoint.  
  
6.  Pro pracovní postupy nainstaluje sestavení pracovního postupu. Umístění, kde můžete změnit pomocí *umístění sestavení* vlastnost.  
  
7.  Pokud je oborem webu či webové, aktivuje funkce projektu ve službě SharePoint. Funkce ve farmě a WebApplication obory nejsou aktivovány.  
  
8.  Pro pracovní postupy, přidruží pracovního postupu knihovny služby SharePoint, seznamu nebo lokality, který jste vybrali v **Průvodce vlastním nastavením SharePoint**.  
  
    > [!NOTE]  
    >  Toto přidružení dojde pouze v případě, že jste vybrali **automaticky přidružení pracovního postupu** v průvodci.  
  
9. Spouští příkazy přizpůsobitelné po nasazení.  
  
10. Připojí [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] ladicího programu na [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)] procesu (*w3wp.exe*). Pokud typ projektu můžete změnit *řešení v izolovaném prostoru* vlastnost a její hodnota je nastavena na **true**, pak připojí ladicí program k jiným procesem (*SPUCWorkerProcess.exe*). Další informace najdete v tématu [aspekty řešení v izolovaném prostoru](../sharepoint/sandboxed-solution-considerations.md).  
  
11. Ladicí program JavaScript spustí, pokud řešení služby SharePoint je řešení farmy.  
  
12. Zobrazí příslušnou knihovnu, seznamu nebo stránka ve webovém prohlížeči.  
  
 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] Zobrazí stavové zprávy v okně výstupu. Po dokončení každé úlohy. Pokud úloha nemůže být dokončena, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] zobrazí chybovou zprávu v okně Seznam chyb.  
  
## <a name="sharepoint-project-features"></a>Funkce projektu služby SharePoint
 Funkce je jednotka přenosné a modulární funkci, která zjednodušuje úpravy lokalit pomocí definice webů. Je také balíček [!INCLUDE[sharepointShort](../sharepoint/includes/sharepointshort-md.md)] elementy (WSS), může být aktivovaný pro konkrétní obor a který pomáhá uživatelům provádět určité cíle nebo úkolu. Šablony jsou nasazeny jako funkce.  
  
 Když na projekt v režimu ladění, proces nasazení vytvoří složku v *funkce* adresář na *%COMMONPROGRAMFILES%\Microsoft Shared\web server extensions\14\TEMPLATE\FEATURES*. Funkce názvy mají formát *název projektu*_Feature*x*, jako je například TestProject_Feature1.  
  
 Obsahuje složky na řešení v adresáři funkce *definice funkce* souboru a *definice pracovního postupu* souboru. Soubor definice funkce (souboru funkce.XML) popisuje soubory v souboru projektu funkci projektu definice (*Elements.xml*) popisuje šablona projektu. *Elements.xml* lze nalézt v **Průzkumníku**, ale souboru funkce.XML se vygeneruje při vytvoření balíčku řešení. Další informace o těchto souborech najdete v tématu [SharePoint projekt a projekt šablon položek](../sharepoint/sharepoint-project-and-project-item-templates.md).  
  
## <a name="debug-workflows"></a>Ladění pracovních postupů
 Když ladíte projekty workflow [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] přidá šablonu pracovního postupu (v závislosti na jeho typu) do knihovny nebo do seznamu. Pracovní postup šablony potom můžete spustit ručně nebo pomocí přidání nebo aktualizace položku. Pak můžete použít [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] k ladění pracovního postupu.  
  
> [!NOTE]  
>  Pokud přidáte odkazy na další sestavení, ujistěte se, zda jsou nainstalovány tyto sestavení v globální mezipaměti sestavení ([!INCLUDE[TLA2#tla_gac](../sharepoint/includes/tla2sharptla-gac-md.md)]). Řešení pracovního postupu, jinak nebude úspěšná. Informace o tom, jak nainstalovat sestavení najdete v tématu [ručně spustit pracovní postup v dokumentu nebo položce](https://support.office.com/article/Manually-start-a-workflow-on-a-document-or-item-5C106E0E-6FF2-4A75-AF99-F01653BC7963).  
  
 Proces nasazení ale nespustí pracovního postupu. Z webu služby SharePoint je nutné spustit pracovní postup. Pracovní postup můžete spustit také pomocí klientské aplikace jako je například Microsoft Office Word 2010 nebo pomocí samostatných kódu na straně serveru. Použijte jeden z přístupů, zadaný v **Průvodce vlastním nastavením SharePoint**.  
  
 Například pokud jste zadali, že pracovní postup lze spustit ručně, spusťte pracovní postup přímo z položky v seznamu nebo knihovny. Další informace o tom, jak ručně spustit pracovní postup najdete v tématu [ručně spustit pracovní postup na položku dokumentu](https://support.office.com/article/Manually-start-a-workflow-on-a-document-or-item-5C106E0E-6FF2-4A75-AF99-F01653BC7963).  
  
## <a name="debug-feature-event-receivers"></a>Ladění přijímačů událostí funkce
 Ve výchozím nastavení při spuštění [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] aplikace služby SharePoint, jeho funkce jsou automaticky aktivované pro vás na serveru SharePoint. Však dojde k potížím při ladění přijímačů událostí funkce, protože když je aktivován funkce [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], běží v jiném procesu než ladicího programu. To znamená, že některé funkce ladění, jako je například zarážky, nebudou fungovat správně.  
  
 Pokud chcete zakázat automatickou aktivaci funkce ve službě SharePoint a povolit správné ladění přijímačů událostí funkce, nastavte hodnotu projektu **aktivní konfigurace nasazení** vlastnost, která má **bez aktivace** před ladění. Potom po spuštění k ladění aplikace SharePoint v [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], je nutné ručně aktivovat funkci ve službě SharePoint. Pokud chcete aktivovat funkci, otevřete **Akce webu** nabídky ve službě SharePoint, zvolte **nastavení lokality**, vyberte **spravovat funkce lokality** propojit a potom zvolte **Aktivovat** tlačítko vedle funkci, chcete-li pokračovat, ladění jako normální.  
  
## <a name="enable-enhanced-debug-information"></a>Povolit rozšířené ladicí informace
 Z důvodu někdy složité interakce mezi [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] procesu (devenv.exe), [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint hostitelského procesu (*vssphost4.exe*), SharePoint a vrstva WCF, diagnostikování chyb vzniklých při vytváření, nasazování a tak dále, může být složité. Chcete-li vyřešte tyto chyby, můžete povolit rozšířené ladicí informace. Chcete-li to provést, přejděte na následující klíč registru v registru systému Windows:  
  
 **HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\11.0\SharePointTools**  
  
 Pokud "EnableDiagnostics" **REG_DWORD** hodnota ještě neexistuje, vytvořte ho ručně. Nastavte hodnotu "EnableDiagnostics" na "1".  
  
 Nastavení této hodnoty klíče 1 příčiny zásobníku trasování informace, které se zobrazí v **výstup** okně vždy, když při spuštění dojít k chybám systému projektu [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]. Chcete-li zakázat rozšířené ladicí informace, nastavte EnableDiagnostics zpět na hodnotu 0 nebo odstranit hodnotu.  
  
 Další informace o jiných klíčů registru služby SharePoint, naleznete v části [ladění rozšíření pro nástroje služby SharePoint v sadě Visual Studio](../sharepoint/debugging-extensions-for-the-sharepoint-tools-in-visual-studio.md).  
  
## <a name="see-also"></a>Viz také:
 [Řešení potíží s řešení služby SharePoint](../sharepoint/troubleshooting-sharepoint-solutions.md)  
  
