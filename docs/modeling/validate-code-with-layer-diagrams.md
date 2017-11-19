---
title: "Ověřování kódu pomocí diagramů závislostí | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- dependency diagrams, validating
- validation, dependency diagrams
- validation, code
- code exploration, validating
- architecture, validating
- Visual Studio Ultimate, validating code
- validation, architecture
- validation, dependencies
- MSBuild, tasks
- MSBuild, dependency diagrams
- MSBuild, validating code
ms.assetid: 70cbe55d-4b33-4355-b0a7-88c770a6f75c
caps.latest.revision: "82"
author: alexhomer1
ms.author: ahomer
manager: douge
ms.openlocfilehash: c6c5954cdb4979ede5e43d2052801ca399f128fd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
---
# <a name="validate-code-with-dependency-diagrams"></a>Ověřování kódu pomocí diagramů závislostí

**Nejnovější informace**: najdete v části [tomto příspěvku na blogu](https://blogs.msdn.microsoft.com/visualstudioalm/2016/11/30/live-dependency-validation-in-visual-studio-2017/).

[Video: Ověření svoje závislosti architektury v reálném čase](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4) 

## <a name="why-use-dependency-diagrams"></a>Proč používat diagramy závislostí?

Pokud chcete mít jistotu, že kód není v konfliktu s návrh, ověřování kódu pomocí diagramů závislostí v sadě Visual Studio. To může pomoci při:  
  
-   Najít konflikty mezi ve vašem kódu závislosti a závislosti v diagramu závislostí.  
  
-   Vyhledání závislostí, které mohou být ovlivněny navrhovanými změnami.  
  
     Například můžete upravit diagram závislostí zobrazit potenciální architektura změny a potom ověřit kód, který najdete v části ovlivněných závislosti.  
  
-   Refaktorujte nebo přeneste kód do jiného návrhu.  
  
     Vyhledejte kód nebo závislosti, které vyžadují práci při přenesení kódu do jiné architektury.  
  
 **Požadavky**  
  
-   Visual Studio  
  
-   Chcete-li ověřit kód automaticky s Team Foundation Build Visual Studio na serveru Team Foundation Build  
  
-   Řešení s projektem modelování s diagram závislostí. Tento diagram závislostí musí být propojena na artefakty v projektech Visual C# .NET nebo Visual Basic .NET, které chcete ověřit. V tématu [vytváření diagramů závislost z vašeho kódu](../modeling/create-layer-diagrams-from-your-code.md).  
  
 Tuto funkci podporovat kterou verzí sady Visual Studio najdete v tématu [verze podpora architektura a modelování nástroje](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport).  
  
 Můžete ověřit kód ručně z diagramu otevřete závislosti v sadě Visual Studio nebo z příkazového řádku. Kód lze rovněž automaticky ověřit při spuštění místních sestavení nebo procesu Team Foundation Build. V tématu [Channel 9 Video: návrh a ověřte vaší architektury pomocí závislostí diagramy](http://go.microsoft.com/fwlink/?LinkID=252073).  
  
> [!IMPORTANT]
>  Pokud chcete spustit ověření vrstev s Team Foundation Build, je nutné také nainstalovat stejné verzi sady Visual Studio na vašem serveru sestavení.  
  
-   [Pokud položku podporuje ověřování](#SupportsValidation)  
  
-   [Zahrnout další sestavení .NET a projektů pro ověření](#IncludeReferences)  
  
-   [Ověření kódu ručně](#ValidateManually)  
  
-   [Ověření kódu automaticky](#ValidateAuto)  
  
-   [Řešení potíží s problémy ověření vrstvy](#TroubleshootingValidation)  
  
-   [Rady pro pochopení a řešení chyb při ověřování vrstvy](#UnderstandingValidationErrors)  

## <a name="live-dependency-validation"></a>Ověření za provozu závislostí

V této verzi sady Visual Studio dojde k ověření závislostí v reálném čase a chyby se okamžitě zobrazí v okně Seznam chyb Visual Studio.

* Ověření za provozu je podporována pro C# a Visual Basic.NET. 

* Chcete-li povolit úplnou analýzu řešení, pokud používáte ověřování za provozu závislostí, otevřete nastavení možnosti z gold panelu, který se zobrazí v seznamu chyb. 
 - Pokud si nejste nepotřebujete vidět všechny architektury problémy ve vašem řešení můžete trvale zavřít tento gold panelu.
 - Pokud nepovolíte úplnou analýzu řešení, se jenom pro soubory upravovaný provádí analýzu.<p /> 

* Při provádění upgrade projektů pro povolení ověřování za provozu, zobrazí se dialogové okno zobrazí průběh převod.

* Při aktualizaci projektu pro ověření provozu závislostí, verze balíčku NuGet se upgraduje na stejný pro všechny projekty a je nejvyšší verze používán. 

* Přidání nové aktivační události závislosti projektu ověření projektu aktualizace. 
  
##  <a name="SupportsValidation"></a>Pokud položku podporuje ověřování  
 Můžete propojit vrstvy weby, dokumentů Office, souborů ve formátu prostého textu a soubory v projektech, které jsou sdíleny mezi více aplikacemi, ale nesmí je zahrnovat proces ověření. Chyby ověřování se neobjeví pro odkazy na projekty nebo sestavení, které jsou připojeny k samostatným vrstvám a v případě, že se mezi těmito vrstvami neobjeví závislosti. Tyto odkazy jsou považovány za závislosti jen tehdy, pokud kód tyto odkazy používá.  
  
1.  Diagram závislost, vyberte jednu nebo více vrstev, klikněte pravým tlačítkem na výběr a potom klikněte na **zobrazení odkazy**.  
  
2.  V **vrstvy Explorer**, podívejte se na **podporuje ověřování** sloupce. Pokud je hodnota false, položka ověřování nepodporuje.  
  
##  <a name="IncludeReferences"></a>Zahrnout další sestavení .NET a projektů pro ověření  
 Při přetahování položek na diagram závislostí, odkazy na odpovídající sestavení .NET nebo projekty jsou automaticky přidáni do portálu **vrstvu odkazů** složky v projektu modelování. Tato složka obsahuje odkazy na sestavení a projekty, které jsou analyzovány během ověřování. Bez ručně je přetáhnete diagram závislostí můžete zahrnout další sestavení .NET a projektů pro ověření.  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt modelování nebo **vrstvu odkazů** složku a pak klikněte na tlačítko **přidat odkaz na**.  
  
2.  V **přidat odkaz na** dialogové okno, vyberte sestavení nebo projekty a pak klikněte na tlačítko **OK**.  
  
##  <a name="ValidateManually"></a>Ověření kódu ručně  
 Pokud máte diagramu otevřete závislostí, propojené položky řešení, můžete spustit **ověřením** příkaz místní z diagramu. Do příkazového řádku můžete také použít ke spuštění **msbuild** s **/p:ValidateArchitecture** vlastní vlastnost nastavena na **True**. Například lze při provádění změn v kódu provádět pravidelně ověřování vrstvy, takže bude možné zachytit konflikty závislostí včas.  
  
#### <a name="to-validate-code-from-an-open-dependency-diagram"></a>Ověření kódu z diagramu otevřete závislostí   
  
1.  Klikněte pravým tlačítkem na povrch diagramu a pak klikněte na tlačítko **ověření architektura**.  
  
    > [!NOTE]
    >  Ve výchozím nastavení **akce sestavení** na soubor závislostí diagram (.layerdiagram) je nastavena na **ověřením** tak, aby na diagramu je součástí procesu ověření.  
  
     **Seznam chyb** okno sestavy všechny chyby, ke kterým dochází. Další informace o chybách ověření najdete v tématu [Rady pro pochopení a řešení chyb při ověřování vrstvy](#UnderstandingValidationErrors).  
  
2.  Chcete-li zobrazit zdroj jednotlivé chyby, dvakrát klikněte na chybu v **seznam chyb** okno.  
  
    > [!NOTE]
    >  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]Mapa kódu může zobrazit místo zdroji této chyby. K tomu dochází, pokud kód je závislý na sestavení, které není specifikováno diagram závislostí nebo kód chybí závislost, která je zadána diagram závislostí. Zkontrolujte Mapa kódu nebo kód k určení, zda by měla existovat závislosti. Další informace o map kódu najdete v tématu [mapování závislostí napříč vaším řešením](../modeling/map-dependencies-across-your-solutions.md).  
  
3.  Chcete-li spravovat chyby, přečtěte si téma [spravovat chyby ověření](#ManageErrors).  
  
#### <a name="to-validate-code-at-the-command-prompt"></a>Ověřování kódu v příkazovém řádku  
  
1.  Otevřete [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] příkazového řádku.  
  
2.  Vyberte jednu z následujících možností:  
  
    -   Chcete-li ověření kódu s projektem modelování konkrétní v řešení, spusťte [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] pomocí následující vlastní vlastnosti.  
  
        ```  
        msbuild <FilePath+ModelProjectFileName>.modelproj /p:ValidateArchitecture=true  
        ```  
  
         - nebo –  
  
         Přejděte do složky, která obsahuje modelování souboru (.modelproj) a diagram závislosti projektu a spusťte [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] pomocí následující vlastní vlastnosti:  
  
        ```  
        msbuild /p:ValidateArchitecture=true   
        ```  
  
    -   Chcete-li ověřit kód na všechny projekty modelování v řešení, spusťte [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] pomocí následující vlastní vlastnosti:  
  
        ```  
        msbuild <FilePath+SolutionName>.sln /p:ValidateArchitecture=true   
        ```  
  
         - nebo –  
  
         Přejděte do složky řešení, které musí obsahovat projekt modelování, který obsahuje diagram závislostí a poté spusťte [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] pomocí následující vlastní vlastnosti:  
  
        ```  
        msbuild /p:ValidateArchitecture=true  
        ```  
  
     Zobrazí se všechny chyby, ke kterým dochází. Další informace o [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], najdete v části [MSBuild](../msbuild/msbuild.md) a [úlohy nástroje MSBuild](../msbuild/msbuild-task.md).  
  
 Další informace o chybách ověření najdete v tématu [Rady pro pochopení a řešení chyb při ověřování vrstvy](#UnderstandingValidationErrors).  
  
###  <a name="ManageErrors"></a>Správa chyb při ověřování  
 Během procesu vývoje můžete chtít potlačit některé vykázané konflikty během ověřování. Například můžete chtít potlačit chyby, které již řešíte nebo které nejsou relevantní k danému scénáři. Pokud potlačíte chybu, je dobrým zvykem přihlásit pracovní položku [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)].  
  
> [!WARNING]
>  Je již připojen k TFS zdrojového kódu ovládacího prvku (SCC) se vytvořit nebo připojit k pracovní položce. Pokud se pokusíte otevřít připojení k jiné SCC sady TFS, Visual Studio automaticky zavře aktuální řešení. Ujistěte se, že jste již připojeni k příslušné SCC před pokusem o vytvořit nebo připojit k pracovní položce. Příkazy nabídky v pozdějších verzích sady Visual Studio, nejsou k dispozici, pokud nejsou připojeni k SCC.  
  
##### <a name="to-create-a-work-item-for-a-validation-error"></a>Vytvoření pracovní položky pro chybu ověřování  
  
-   V **seznam chyb** okna, klikněte pravým tlačítkem na chyby, přejděte na **vytvoření pracovní položky**a pak klikněte na typ pracovní položky, které chcete vytvořit.  
  
 Pomocí těchto úloh můžete spravovat chyb při ověřování v **seznam chyb** okno:  
  
|**K**|**Postupujte podle těchto kroků**|  
|------------|----------------------------|  
|Potlačení vybraných chyb během ověřování|Klikněte pravým tlačítkem na jeden nebo více vybraných chyby, přejděte na **spravovat chyby ověření**a potom klikněte na **potlačit chyby**.<br /><br /> Potlačené chyby se zobrazují s přeškrtnutím. Při příštím spuštění ověřování se tyto chyby nezobrazí.<br /><br /> Potlačená chyby jsou sledovány v souboru .suppressions pro odpovídající soubor diagram závislostí.|  
|Ukončení potlačování vybraných chyb|Klikněte pravým tlačítkem na vybrané Potlačená chyby nebo chyby, přejděte na **spravovat chyby ověření**a potom klikněte na **zastavit potlačit chyby**.<br /><br /> Vybrané potlačené chyby se při příštím spuštění ověřování zobrazí.|  
|Obnovit všechny Potlačená chyby v **seznam chyb** okna|Klikněte pravým tlačítkem na libovolné místo v **seznam chyb** okno, přejděte na příkaz **spravovat chyby ověření**a potom klikněte na **zobrazit všechny chyby potlačit**.|  
|Skrýt všechny Potlačená chyby z **seznam chyb** okna|Klikněte pravým tlačítkem na libovolné místo v **seznam chyb** okno, přejděte na příkaz **spravovat chyby ověření**a potom klikněte na **skrýt všechny chyby potlačit**.|  
  
##  <a name="ValidateAuto"></a>Ověření kódu automaticky  
 Ověřování vrstev lze provádět při každém spuštění místního sestavení. Pokud váš tým používá proces Team Foundation Build, můžete provést ověření vrstev s ověřenými vráceními se změnami, které lze určit vytvořením vlastní úlohy MSBuild, a použít sestavy sestavení pro sběr chyb ověřování. Vytvoření sestavení ověřovaného vrácení se změnami, naleznete v části [ověřit změny pomocí procesu ověřované vrácení se změnami sestavení](http://msdn.microsoft.com/Library/9cfc8b9c-1023-40fd-8ab5-1b1bd9c172ec).  
  
#### <a name="to-validate-code-automatically-during-a-local-build"></a>Automatické ověřování kódu během místního sestavení  
  
-   K otevření souboru projektu modelování (.modelproj) použijte textový editor a následně vložte následující vlastnost:  
  
```  
<ValidateArchitecture>true</ValidateArchitecture>  
```  
  
 \-nebo –  
  
1.  V **Průzkumníku řešení**, klikněte pravým tlačítkem na projekt modelování, který obsahuje diagram závislostí nebo diagramy a pak klikněte na tlačítko **vlastnosti**.  
  
2.  V **vlastnosti** nastavte projekt modelování **ověření architektura** vlastnost **True**.  
  
     To zahrne projekt modelování do ověřovacího procesu.  
  
3.  V **Průzkumníku**, klikněte na soubor závislostí diagram (.layerdiagram), který chcete použít pro ověření.  
  
4.  V **vlastnosti** okna, ujistěte se, že diagramu **akce sestavení** je nastavena na **ověřením**.  
  
     To zahrnuje diagram závislostí v procesu ověřování.  
  
 Ke správě chyby v okně Seznam chyb, najdete v části [spravovat chyby ověření](#ManageErrors).  
  
#### <a name="to-validate-code-automatically-during-a-team-foundation-build"></a>Ověření kódu automaticky během sestavení Team Foundation Build  
  
1.  V **Team Explorer**, dvakrát klikněte na definici sestavení a pak klikněte na tlačítko **proces**.  
  
2.  V části **parametry procesu sestavení**, rozbalte položku **kompilace**a zadejte následující příkaz v **argumenty MSBuild** parametr:  
  
     `/p:ValidateArchitecture=true`  
  
 Další informace o chybách ověření najdete v tématu [Rady pro pochopení a řešení chyb při ověřování vrstvy](#UnderstandingValidationErrors). Další informace o [!INCLUDE[esprbuild](../misc/includes/esprbuild_md.md)], najdete v části:  
  
-   [Sestavení aplikace](http://msdn.microsoft.com/Library/a971b0f9-7c28-479d-a37b-8fd7e27ef692)  
  
-   [Použít výchozí šablonu pro vaše procesu sestavení](http://msdn.microsoft.com/Library/43930b12-c21b-4599-a980-2995e3d16e31)  
  
-   [Upravit starší verze sestavení, která je založená na UpgradeTemplate.xaml](http://msdn.microsoft.com/Library/ee1a8259-1dd1-4a10-9563-66c5446ef41c)  
  
-   [Přizpůsobení šablony procesu sestavení](http://msdn.microsoft.com/Library/b94c58f2-ae6f-4245-bedb-82cd114f6039)  
  
-   [Monitorování průběhu spuštění sestavení](http://msdn.microsoft.com/Library/e51e3bad-2d1d-4b7b-bfcc-c43439c6c8ef)  
  
##  <a name="TroubleshootingValidation"></a>Řešení potíží s problémy ověření vrstvy  
 Následující tabulka popisuje problémy s ověřením vrstvy a jejich řešení. Tyto problémy se liší od chyb, které vzniknou z konfliktů mezi kódem a návrhem. Další informace o těchto chybách naleznete v části [Rady pro pochopení a řešení chyb při ověřování vrstvy](#UnderstandingValidationErrors).  
  
|**Problém**|**Možná příčina**|**Řešení**|  
|---------------|------------------------|--------------------|  
|Chyby ověřování se nezobrazí podle očekávání.|Ověření v diagramech závislostí, který jste zkopírovali z jiných diagramů závislostí v Průzkumníku řešení a které jsou ve stejném projektu modelování nefunguje. diagramy závislosti, které jste zkopírovali tímto způsobem obsahovat stejné odkazy jako původní diagram závislostí.|Přidání nového diagramu závislost na projekt modelování.<br /><br /> Zkopírujte elementy z diagram závislostí zdroje k novému diagramu.|  
  
##  <a name="UnderstandingValidationErrors"></a>Pochopení a řešení chyb při ověřování vrstvy  
 Když ověřujete kód proti diagram závislostí, dochází k chybám ověření, když kód je v konfliktu s návrhu. Chyby ověřování mohou způsobit například následující podmínky:  
  
-   Artefakt je přiřazen nesprávné vrstvě. V tomto případě přesuňte artefakt.  
  
-   Artefakt, jako je například třída, používá jiné třídy způsobem, který je v konfliktu s architekturou. V tomto případě refaktorujte kód a odeberte závislost.  
  
 Chcete-li tyto chyby odstranit, aktualizujte kód, dokud se během ověřování neobjeví žádné chyby. Tuto úlohu lze provést iteračním způsobem.  
  
 Následující oddíl popisuje syntaxi, která se u těchto chyb používá, vysvětluje význam těchto chyb a navrhne, jak je vyřešit nebo spravovat.  
  
|**Syntaxe**|**Popis**|  
|----------------|---------------------|  
|*ArtifactN*(*ArtifactTypeN*)|*ArtifactN* je artefakt, která souvisí s vrstvou, Diagram závislostí.<br /><br /> *ArtifactTypeN* je typ *ArtifactN*, například **třída** nebo **metoda**, například:<br /><br /> MySolution.MyProject.MyClass.MyMethod(Method)|  
|*NamespaceNameN*|Název oboru názvů.|  
|*LayerNameN*|Název vrstvy v diagramu závislostí.|  
|*DependencyType*|Typ relace závislosti mezi *Artifact1* a *Artifact2*. Například *Artifact1* má **volání** vztah s *Artifact2*.|  
  
|**Chyba syntaxe**|**Popis chyby**|  
|----------------------|---------------------------|  
|DV0001: **neplatné závislosti**|Tento problém je uvedená, pokud element kódu (obor názvů, typ, člen) namapované vrstvu odkazů na element kódu namapovaný na jinou vrstvu, ale neexistuje žádné šipku závislost mezi tyto vrstvy v diagramu ověření závislostí obsahující této vrstvy. Toto je porušení omezení závislostí.|  
|DV1001: **název neplatný obor názvů.**|Tento problém je uvedená na element kódu související s vrstvou, pro kterou se vlastnost "Povolené názvy Namespace" neobsahuje obor názvů, ve kterém je definovaný tento element kódu. Toto je pojmenování porušení omezení. Všimněte si, že má být středníkem seznam obory názvů v kódu, které jsou elementy související s vrstvou syntaxe "Povolené názvy Namespace" mohou být definován.|  
|DV1002: **závislost na unreferenceable obor názvů**|Tento problém je uvedená na element kódu související s vrstvou a odkazování na jiný kód element definovaný v oboru názvů, které je definováno v "Unreferenceable Namespace" vlastnost vrstvy. Toto je pojmenování porušení omezení. Všimněte si, že vlastnost "Unreferenceable obory názvů" je definován jako seznam středníkem oddělené obory názvů, který by neměl být odkazuje v elementy kódu přidružené k této vrstvy.|  
|DV1003: **název oboru názvů Nepovoleno**|Tento problém je uvedená na element kódu související s vrstvou, pro kterou se vlastnost "Nepovolené Namespace názvy" obsahuje obor názvů, ve kterém je definovaný tento element kódu. Toto je pojmenování porušení omezení. Všimněte si, že vlastnost "Název oboru názvů Nepovoleno" je definován jako seznam středníkem oddělené obory názvů, ve které kódu nesmí být definována prvky přidružené k této vrstvy.|  
|DV3001: **Missing Link**|Vrstva se*LayerName*, obsahuje odkazy na'*artefaktů*, který nebyl nalezen. Nechybí odkaz na sestavení?|*LayerName* odkazy na artefakt, který nebyl nalezen. Odkaz na třídu může chybět například proto, že projekt modelování nemá odkaz na sestavení obsahující třídu.|  
|DV9001: **architektury analysis nalézt vnitřní chyby**|Výsledky nemusí být úplné. Další informace lze nalézt v podrobném protokolu událostí sestavení nebo ve výstupním okně.|Více podrobností lze nalézt v protokolu událostí sestavení nebo ve výstupním okně.|  

 
## <a name="see-also"></a>Viz také  
 [Ověřování systému během vývoje](../modeling/validate-your-system-during-development.md)   
 [Video: Ověření svoje závislosti architektury v reálném čase](https://sec.ch9.ms/sessions/69613110-c334-4f25-bb36-08e5a93456b5/170ValidateArchitectureDependenciesWithVisualStudio.mp4)   
