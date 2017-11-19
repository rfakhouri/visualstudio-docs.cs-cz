---
title: "Referenční dokumentace úlohy nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords: MSBuild, tasks
ms.assetid: b3144b27-a426-4259-b8ae-5f7991b202b6
caps.latest.revision: "32"
author: kempb
ms.author: kempb
manager: ghogen
ms.openlocfilehash: c0d1474fb03acd838387677786656967e852fdf9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="msbuild-task-reference"></a>Referenční dokumentace úlohy nástroje MSBuild
Úlohy zadejte kód, který spouští během procesu sestavení. Úlohy v následujícím seznamu jsou součástí [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Když [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] je nainstalovaná, další úlohy jsou k dispozici, které se používají k vytvoření [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projekty. Další informace najdete v tématu [úlohy Visual C++](../msbuild/msbuild-tasks-specific-to-visual-cpp.md).  
  
 Kromě parametry uvedené v tématech v této části každý úkol má také následující parametry:  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Condition`|Volitelné `String` parametr.<br /><br /> A `Boolean` výrazu, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] modul se používá k určení, zda tato úloha bude provádět. Informace o podmínkách, které jsou podporovány [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], najdete v části [podmínky](../msbuild/msbuild-conditions.md).|  
|`ContinueOnError`|Volitelný parametr. Může obsahovat jednu z následujících hodnot:<br /><br /> -   **WarnAndContinue** nebo **true**. Pokud úloha selže, úlohy v [cíl](../msbuild/target-element-msbuild.md) elementu a sestavení dále provést, a všechny chyby z úlohy se považují za upozornění.<br />-   **ErrorAndContinue**. Pokud úloha selže, úlohy v `Target` elementu a sestavení dále provést, a všechny chyby z úlohy se považují za chyby.<br />-   **ErrorAndStop** nebo **false** (výchozí). Pokud úloha selže, ve zbývajících úkolech v `Target` elementu a sestavení nebudou provedeny a celý `Target` elementu a sestavení považován za neúspěšný.<br /><br /> Verze rozhraní .NET Framework před 4.5 podporovaná jenom `true` a `false` hodnoty.<br /><br /> Další informace najdete v tématu [postupy: ignorování chyb v úlohách](../msbuild/how-to-ignore-errors-in-tasks.md).|  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Třída Base úlohy](../msbuild/task-base-class.md)  
 Přidá do úlohy, které jsou odvozeny od několik parametrů <xref:Microsoft.Build.Utilities.Task> třídy.  
  
 [Taskextension – základní třída](../msbuild/taskextension-base-class.md)  
 Přidá do úlohy, které jsou odvozeny od několik parametrů <xref:Microsoft.Build.Tasks.TaskExtension> třídy.  
  
 [Tooltaskextension – základní třída](../msbuild/tooltaskextension-base-class.md)  
 Přidá do úlohy, které jsou odvozeny od několik parametrů <xref:Microsoft.Build.Tasks.ToolTaskExtension> třídy.  
  
 [AL (Linker sestavení) – úloha](../msbuild/al-assembly-linker-task.md)  
 Vytvoří sestavení s manifestu z jeden nebo více souborů, které jsou buď moduly nebo soubory prostředků.  
  
 [AspNetCompiler – úloha](../msbuild/aspnetcompiler-task.md)  
 Zabalí aspnet_compiler.exe, nástroj předkompilovat aplikace ASP.NET.  
  
 [Assignculture – úloha](../msbuild/assignculture-task.md)  
 Přiřadí identifikátory jazykové verze položky.  
  
 [Assignprojectconfiguration – úloha](../msbuild/assignprojectconfiguration-task.md)  
 Přijímá seznam řetězců, konfigurace a přiřadí zadaný projekty.  
  
 [Assigntargetpath – úloha](../msbuild/assigntargetpath-task.md)  
 Přijme seznam souborů a přidá `<TargetPath>` atributy, když už nejsou zadané.  
  
 [Calltarget – úloha](../msbuild/calltarget-task.md)  
 Vyvolá cíl v souboru projektu.  
  
 [CombinePath – úloha](../msbuild/combinepath-task.md)  
 Spojuje do jednu cestu zadané cesty.  
  
 [Converttoabsolutepath – úloha](../msbuild/converttoabsolutepath-task.md)  
 Převede relativní cestu nebo odkaz na absolutní cestu.  
  
 [Copy – úloha](../msbuild/copy-task.md)  
 Zkopíruje soubory do nového umístění.  
  
 [Createcsharpmanifestresourcename – úloha](../msbuild/createcsharpmanifestresourcename-task.md)  
 Vytvoří [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]-manifestu název stylu z daného RESX název souboru nebo jiný prostředek.  
  
 [Createitem – úloha](../msbuild/createitem-task.md)  
 Naplní kolekcí položek ze vstupní položek, což položek, který se má zkopírovat z jednoho seznamu do jiného.  
  
 [CreateProperty – úloha](../msbuild/createproperty-task.md)  
 Naplní vlastnosti z vstupní hodnoty, což hodnoty zkopírovány z jednu vlastnost nebo řetězec na jiný.  
  
 [Createvisualbasicmanifestresourcename – úloha](../msbuild/createvisualbasicmanifestresourcename-task.md)  
 Vytvoří [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]-manifestu název stylu z daného RESX název souboru nebo jiný prostředek.  
  
 [CSC – úloha](../msbuild/csc-task.md)  
 Vyvolá kompilátor Visual C# k vytvoření spustitelné soubory, knihovny DLL nebo moduly kódu.  
  
 [Delete – úloha](../msbuild/delete-task.md)  
 Odstraní zadané soubory.  
  
 [Error – úloha](../msbuild/error-task.md)  
 Zastaví sestavení a protokoly chybu založené na příkazu vyhodnotí podmíněného.  
  
 [Exec – úloha](../msbuild/exec-task.md)  
 Spustí zadaný program nebo příkaz pomocí zadaných argumentů.  
  
 [Findappconfigfile – úloha](../msbuild/findappconfigfile-task.md)  
 Vyhledá soubor app.config, pokud existuje v zadané seznamy.  
  
 [Findinlist – úloha](../msbuild/findinlist-task.md)  
 Vyhledá položku v zadané seznamu, který má odpovídající itemspec.  
  
 [Findunderpath – úloha](../msbuild/findunderpath-task.md)  
 Určuje, které položky v kolekci zadaná položka existuje v zadané složce a všechny její podsložky.  
  
 [Formaturl – úloha](../msbuild/formaturl-task.md)  
 Převede adresu URL ve správném formátu adresy URL.  
  
 [Formatversion – úloha](../msbuild/formatversion-task.md)  
 Číslo revize se připojí k číslo verze.  
  
 [Generateapplicationmanifest – úloha](../msbuild/generateapplicationmanifest-task.md)  
 Generuje [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace nebo nativní manifestu.  
  
 [GenerateBootstrapper – úloha](../msbuild/generatebootstrapper-task.md)  
 Poskytuje automatizovaný způsob, jak zjistit, stáhnout a nainstalovat aplikace a její požadované součásti.  
  
 [Generatedeploymentmanifest – úloha](../msbuild/generatedeploymentmanifest-task.md)  
 Generuje [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] – manifest nasazení.  
  
 [Generateresource – úloha](../msbuild/generateresource-task.md)  
 Soubory .txt a RESX převede na běžné soubory .resources binární modulu runtime jazyka.  
  
 [Generatetrustinfo – úloha](../msbuild/generatetrustinfo-task.md)  
 Generuje důvěryhodnosti aplikace od základní manifest a od `TargetZone` a `ExcludedPermissions` parametry.  
  
 [Getassemblyidentity – úloha](../msbuild/getassemblyidentity-task.md)  
 Načte identity sestavení ze zadané soubory a výstupy informací o identitě.  
  
 [Getframeworkpath – úloha](../msbuild/getframeworkpath-task.md)  
 Načte cestu k [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sestavení.  
  
 [Getframeworksdkpath – úloha](../msbuild/getframeworksdkpath-task.md)  
 Načte cestu k [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)].  
  
 [Getreferenceassemblypaths – úloha](../msbuild/getreferenceassemblypaths-task.md)  
 Vrátí odkaz na sestavení cesty různé architektury.  
  
 [LC – úloha](../msbuild/lc-task.md)  
 Generuje soubor .license z .licx – soubor.  
  
 [Makedir – úloha](../msbuild/makedir-task.md)  
 Vytvoří adresářů a v případě potřeby žádné nadřazeného adresáře.  
  
 [Úloha zprávy](../msbuild/message-task.md)  
 Zaznamená zprávu během sestavení.  
  
 [Move – úloha](../msbuild/move-task.md)  
 Soubory přesune do nového umístění.  
  
 [MSBuild – úloha](../msbuild/msbuild-task.md)  
 Sestavení [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projekty z jiné [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projektu.  
  
 [Readlinesfromfile – úloha](../msbuild/readlinesfromfile-task.md)  
 Čte seznam položek z textového souboru.  
  
 [Registerassembly – úloha](../msbuild/registerassembly-task.md)  
 Načte metadata v rámci zadaného sestavení a přidá nezbytné položky registru.  
  
 [Removedir – úloha](../msbuild/removedir-task.md)  
 Odebere zadaný adresářů a všechny jeho soubory a podadresáře.  
  
 [Removeduplicates – úloha](../msbuild/removeduplicates-task.md)  
 Odebere duplicitní položky z kolekce zadanou položku.  
  
 [Requiresframework35sp1assembly – úloha](../msbuild/requiresframework35sp1assembly-task.md)  
 Určuje, zda aplikace vyžaduje rozhraní .NET Framework 3.5 SP1.  
  
 Úloha nástroj ResGen  
 Zastaralé. Použití [generateresource – úloha](../msbuild/generateresource-task.md) úloha pro soubory TXT a RESX převést do a z společné jazykové runtime .resources binární soubory.  
  
 [Resolveassemblyreference – úloha](../msbuild/resolveassemblyreference-task.md)  
 Určuje, které jsou závislé na zadaná sestavení ve všech sestaveních.  
  
 [Resolvecomreference – úloha](../msbuild/resolvecomreference-task.md)  
 Přebírá seznam jeden nebo více názvy knihovny typů, nebo soubory .tlb a řeší tyto knihoven typů do umístění na disku.  
  
 [Resolvekeysource – úloha](../msbuild/resolvekeysource-task.md)  
 Určuje zdroj klíče silným názvem  
  
 [Resolvemanifestfiles – úloha](../msbuild/resolvemanifestfiles-task.md)  
 Následující položky v procesu sestavení přeloží na soubory pro generování manifestu: vytvořené položky, závislostí, satelity, obsahu, symboly ladění a dokumentaci.  
  
 [Resolvenativereference – úloha](../msbuild/resolvenativereference-task.md)  
 Přeloží nativní odkazy.  
  
 [Resolvenonmsbuildprojectoutput – úloha](../msbuild/resolvenonmsbuildprojectoutput-task.md)  
 Určuje výstupní soubory pro bez MSBuild odkazy na projekt.  
  
 [SGen – úloha](../msbuild/sgen-task.md)  
 Vytvoří sestavení serializace XML pro typy v zadaném sestavení.  
  
 [Signfile – úloha](../msbuild/signfile-task.md)  
 Zadaný soubor pomocí zadaný certifikát podepíše.  
  
 [Touch – úloha](../msbuild/touch-task.md)  
 Nastaví dobu přístup a úpravy souborů.  
  
 [Unregisterassembly – úloha](../msbuild/unregisterassembly-task.md)  
 Zruší registraci na zadaná sestavení pro účely zprostředkovatele komunikace s objekty COM.  
  
 [Updatemanifest – úloha](../msbuild/updatemanifest-task.md)  
 Aktualizace vybraných vlastností v manifestu a odstoupí.  
  
 [Vbc – úloha](../msbuild/vbc-task.md)  
 Vyvolá Visual Basic – kompilátor k vytvoření spustitelné soubory, knihovny DLL nebo moduly kódu...  
  
 [Warning – úloha](../msbuild/warning-task.md)  
 Protokoly upozornění během sestavení založené na příkazu vyhodnotí podmíněného.  
  
 [Writecodefragment – úloha](../msbuild/writecodefragment-task.md)  
 Generuje soubor dočasné kódu pomocí fragmentu generovaného kódu. Nedojde k odstranění souboru.  
  
 [Writelinestofile – úloha](../msbuild/writelinestofile-task.md)  
 Zapíše zadaných položek pro zadaný textový soubor.  
  
 [Xmlpeek – úloha](../msbuild/xmlpeek-task.md)  
 Vrátí hodnoty podle specifikace dotaz XPath ze souboru XML.  
  
 [Xmlpoke – úloha](../msbuild/xmlpoke-task.md)  
 Nastaví hodnoty podle specifikace dotaz XPath do souboru XML.  
  
 [Xsltransformation – úloha](../msbuild/xsltransformation-task.md)  
 Transformuje vstup XML pomocí *rozšiřitelný jazyk transformace šablony stylů* (XSLT) nebo zkompilovat XSLT a výstupy do výstupní zařízení nebo souboru.  
  
## <a name="see-also"></a>Viz také  
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Zápis úloh](../msbuild/task-writing.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)