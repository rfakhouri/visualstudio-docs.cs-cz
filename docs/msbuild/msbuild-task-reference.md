---
title: "Referenční dokumentace úlohy nástroje MSBuild | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: msbuild
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, tasks
ms.assetid: b3144b27-a426-4259-b8ae-5f7991b202b6
caps.latest.revision: 
author: Mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload:
- multiple
ms.openlocfilehash: 1d3bd0cb011dd99183e3d7318693261e19e01791
ms.sourcegitcommit: 205d15f4558315e585c67f33d5335d5b41d0fcea
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/09/2018
---
# <a name="msbuild-task-reference"></a>Referenční dokumentace úlohy nástroje MSBuild
Úlohy zadejte kód, který spouští během procesu sestavení. Úlohy v následujícím seznamu jsou součástí [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]. Když [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] je nainstalovaná, další úlohy jsou k dispozici, které se používají k vytvoření [!INCLUDE[vcprvc](../code-quality/includes/vcprvc_md.md)] projekty. Další informace najdete v tématu [úlohy Visual C++](../msbuild/msbuild-tasks-specific-to-visual-cpp.md).  
  
 Kromě parametry uvedené v tématech v této části každý úkol má také následující parametry:  
  
|Parametr|Popis|  
|---------------|-----------------|  
|`Condition`|Volitelné `String` parametr.<br /><br /> A `Boolean` výrazu, [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] modul se používá k určení, zda tato úloha bude provádět. Informace o podmínkách, které jsou podporovány [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], najdete v části [podmínky](../msbuild/msbuild-conditions.md).|  
|`ContinueOnError`|Volitelný parametr. Může obsahovat jednu z následujících hodnot:<br /><br /> -   **WarnAndContinue** nebo **true**. Pokud úloha selže, úlohy v [cíl](../msbuild/target-element-msbuild.md) elementu a sestavení dále provést, a všechny chyby z úlohy se považují za upozornění.<br />-   **ErrorAndContinue**. Pokud úloha selže, úlohy v `Target` elementu a sestavení dále provést, a všechny chyby z úlohy se považují za chyby.<br />-   **ErrorAndStop** nebo **false** (výchozí). Pokud úloha selže, ve zbývajících úkolech v `Target` elementu a sestavení nebudou provedeny a celý `Target` elementu a sestavení považován za neúspěšný.<br /><br /> Verze rozhraní .NET Framework před 4.5 podporovaná jenom `true` a `false` hodnoty.<br /><br /> Další informace najdete v tématu [postupy: ignorování chyb v úlohách](../msbuild/how-to-ignore-errors-in-tasks.md).|  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Base – základní třída](../msbuild/task-base-class.md)  
 Přidá do úlohy, které jsou odvozeny od několik parametrů <xref:Microsoft.Build.Utilities.Task> třídy.  
  
 [TaskExtension – základní třída](../msbuild/taskextension-base-class.md)  
 Přidá do úlohy, které jsou odvozeny od několik parametrů <xref:Microsoft.Build.Tasks.TaskExtension> třídy.  
  
 [ToolTaskExtension – základní třída](../msbuild/tooltaskextension-base-class.md)  
 Přidá do úlohy, které jsou odvozeny od několik parametrů <xref:Microsoft.Build.Tasks.ToolTaskExtension> třídy.  
  
 [AL (linker sestavení) – úloha](../msbuild/al-assembly-linker-task.md)  
 Vytvoří sestavení s manifestu z jeden nebo více souborů, které jsou buď moduly nebo soubory prostředků.  
  
 [AspNetCompiler – úloha](../msbuild/aspnetcompiler-task.md)  
 Zabalí aspnet_compiler.exe, nástroj předkompilovat aplikace ASP.NET.  
  
 [AssignCulture – úloha](../msbuild/assignculture-task.md)  
 Přiřadí identifikátory jazykové verze položky.  
  
 [AssignProjectConfiguration – úloha](../msbuild/assignprojectconfiguration-task.md)  
 Přijímá seznam řetězců, konfigurace a přiřadí zadaný projekty.  
  
 [AssignTargetPath – úloha](../msbuild/assigntargetpath-task.md)  
 Přijme seznam souborů a přidá `<TargetPath>` atributy, když už nejsou zadané.  
  
 [CallTarget – úloha](../msbuild/calltarget-task.md)  
 Vyvolá cíl v souboru projektu.  
  
 [CombinePath – úloha](../msbuild/combinepath-task.md)  
 Spojuje do jednu cestu zadané cesty.  
  
 [ConvertToAbsolutePath – úloha](../msbuild/converttoabsolutepath-task.md)  
 Převede relativní cestu nebo odkaz na absolutní cestu.  
  
 [Copy – úloha](../msbuild/copy-task.md)  
 Zkopíruje soubory do nového umístění.  
  
 [CreateCSharpManifestResourceName – úloha](../msbuild/createcsharpmanifestresourcename-task.md)  
 Vytvoří [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)]-manifestu název stylu z daného RESX název souboru nebo jiný prostředek.  
  
 [CreateItem – úloha](../msbuild/createitem-task.md)  
 Naplní kolekcí položek ze vstupní položek, což položek, který se má zkopírovat z jednoho seznamu do jiného.  
  
 [CreateProperty – úloha](../msbuild/createproperty-task.md)  
 Naplní vlastnosti z vstupní hodnoty, což hodnoty zkopírovány z jednu vlastnost nebo řetězec na jiný.  
  
 [CreateVisualBasicManifestResourceName – úloha](../msbuild/createvisualbasicmanifestresourcename-task.md)  
 Vytvoří [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]-manifestu název stylu z daného RESX název souboru nebo jiný prostředek.  
  
 [Csc – úloha](../msbuild/csc-task.md)  
 Vyvolá kompilátor Visual C# k vytvoření spustitelné soubory, knihovny DLL nebo moduly kódu.  
  
 [Delete – úloha](../msbuild/delete-task.md)  
 Odstraní zadané soubory.  
  
 [Error – úloha](../msbuild/error-task.md)  
 Zastaví sestavení a protokoly chybu založené na příkazu vyhodnotí podmíněného.  
  
 [Exec – úloha](../msbuild/exec-task.md)  
 Spustí zadaný program nebo příkaz pomocí zadaných argumentů.  
  
 [FindAppConfigFile – úloha](../msbuild/findappconfigfile-task.md)  
 Vyhledá soubor app.config, pokud existuje v zadané seznamy.  
  
 [FindInList – úloha](../msbuild/findinlist-task.md)  
 Vyhledá položku v zadané seznamu, který má odpovídající itemspec.  
  
 [FindUnderPath – úloha](../msbuild/findunderpath-task.md)  
 Určuje, které položky v kolekci zadaná položka existuje v zadané složce a všechny její podsložky.  
  
 [FormatUrl – úloha](../msbuild/formaturl-task.md)  
 Převede adresu URL ve správném formátu adresy URL.  
  
 [FormatVersion – úloha](../msbuild/formatversion-task.md)  
 Číslo revize se připojí k číslo verze.  
  
 [GenerateApplicationManifest – úloha](../msbuild/generateapplicationmanifest-task.md)  
 Generuje [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace nebo nativní manifestu.  
  
 [GenerateBootstrapper – úloha](../msbuild/generatebootstrapper-task.md)  
 Poskytuje automatizovaný způsob, jak zjistit, stáhnout a nainstalovat aplikace a její požadované součásti.  
  
 [GenerateDeploymentManifest – úloha](../msbuild/generatedeploymentmanifest-task.md)  
 Generuje [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] – manifest nasazení.  
  
 [GenerateResource – úloha](../msbuild/generateresource-task.md)  
 Soubory .txt a RESX převede na běžné soubory .resources binární modulu runtime jazyka.  
  
 [GenerateTrustInfo – úloha](../msbuild/generatetrustinfo-task.md)  
 Generuje důvěryhodnosti aplikace od základní manifest a od `TargetZone` a `ExcludedPermissions` parametry.  
  
 [GetAssemblyIdentity – úloha](../msbuild/getassemblyidentity-task.md)  
 Načte identity sestavení ze zadané soubory a výstupy informací o identitě.  
  
 [GetFrameworkPath – úloha](../msbuild/getframeworkpath-task.md)  
 Načte cestu k [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] sestavení.  
  
 [GetFrameworkSdkPath – úloha](../msbuild/getframeworksdkpath-task.md)  
 Načte cestu k [!INCLUDE[winsdklong](../deployment/includes/winsdklong_md.md)].  
  
 [GetReferenceAssemblyPaths – úloha](../msbuild/getreferenceassemblypaths-task.md)  
 Vrátí odkaz na sestavení cesty různé architektury.  
  
 [LC – úloha](../msbuild/lc-task.md)  
 Generuje soubor .license z .licx – soubor.  
  
 [MakeDir – úloha](../msbuild/makedir-task.md)  
 Vytvoří adresářů a v případě potřeby žádné nadřazeného adresáře.  
  
 [Message – úloha](../msbuild/message-task.md)  
 Zaznamená zprávu během sestavení.  
  
 [Move – úloha](../msbuild/move-task.md)  
 Soubory přesune do nového umístění.  
  
 [MSBuild – úloha](../msbuild/msbuild-task.md)  
 Sestavení [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projekty z jiné [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projektu.  
  
 [ReadLinesFromFile – úloha](../msbuild/readlinesfromfile-task.md)  
 Čte seznam položek z textového souboru.  
  
 [RegisterAssembly – úloha](../msbuild/registerassembly-task.md)  
 Načte metadata v rámci zadaného sestavení a přidá nezbytné položky registru.  
  
 [RemoveDir – úloha](../msbuild/removedir-task.md)  
 Odebere zadaný adresářů a všechny jeho soubory a podadresáře.  
  
 [RemoveDuplicates – úloha](../msbuild/removeduplicates-task.md)  
 Odebere duplicitní položky z kolekce zadanou položku.  
  
 [RequiresFramework35SP1Assembly – úloha](../msbuild/requiresframework35sp1assembly-task.md)  
 Určuje, zda aplikace vyžaduje rozhraní .NET Framework 3.5 SP1.  
  
 Úloha nástroj ResGen  
 Zastaralé. Použití [generateresource – úloha](../msbuild/generateresource-task.md) úloha pro soubory TXT a RESX převést do a z společné jazykové runtime .resources binární soubory.  
  
 [ResolveAssemblyReference – úloha](../msbuild/resolveassemblyreference-task.md)  
 Určuje, které jsou závislé na zadaná sestavení ve všech sestaveních.  
  
 [ResolveComReference – úloha](../msbuild/resolvecomreference-task.md)  
 Přebírá seznam jeden nebo více názvy knihovny typů, nebo soubory .tlb a řeší tyto knihoven typů do umístění na disku.  
  
 [ResolveKeySource – úloha](../msbuild/resolvekeysource-task.md)  
 Určuje zdroj klíče silným názvem  
  
 [ResolveManifestFiles – úloha](../msbuild/resolvemanifestfiles-task.md)  
 Následující položky v procesu sestavení přeloží na soubory pro generování manifestu: vytvořené položky, závislostí, satelity, obsahu, symboly ladění a dokumentaci.  
  
 [ResolveNativeReference – úloha](../msbuild/resolvenativereference-task.md)  
 Přeloží nativní odkazy.  
  
 [ResolveNonMSBuildProjectOutput – úloha](../msbuild/resolvenonmsbuildprojectoutput-task.md)  
 Určuje výstupní soubory pro bez MSBuild odkazy na projekt.  
  
 [SGen – úloha](../msbuild/sgen-task.md)  
 Vytvoří sestavení serializace XML pro typy v zadaném sestavení.  
  
 [SignFile – úloha](../msbuild/signfile-task.md)  
 Zadaný soubor pomocí zadaný certifikát podepíše.  
  
 [Touch – úloha](../msbuild/touch-task.md)  
 Nastaví dobu přístup a úpravy souborů.  
  
 [UnregisterAssembly – úloha](../msbuild/unregisterassembly-task.md)  
 Zruší registraci na zadaná sestavení pro účely zprostředkovatele komunikace s objekty COM.  
  
 [UpdateManifest – úloha](../msbuild/updatemanifest-task.md)  
 Aktualizace vybraných vlastností v manifestu a odstoupí.  
  
 [Vbc – úloha](../msbuild/vbc-task.md)  
 Vyvolá Visual Basic – kompilátor k vytvoření spustitelné soubory, knihovny DLL nebo moduly kódu...  
  
 [Warning – úloha](../msbuild/warning-task.md)  
 Protokoly upozornění během sestavení založené na příkazu vyhodnotí podmíněného.  
  
 [WriteCodeFragment – úloha](../msbuild/writecodefragment-task.md)  
 Generuje soubor dočasné kódu pomocí fragmentu generovaného kódu. Nedojde k odstranění souboru.  
  
 [WriteLinesToFile – úloha](../msbuild/writelinestofile-task.md)  
 Zapíše zadaných položek pro zadaný textový soubor.  
  
 [XmlPeek – úloha](../msbuild/xmlpeek-task.md)  
 Vrátí hodnoty podle specifikace dotaz XPath ze souboru XML.  
  
 [XmlPoke – úloha](../msbuild/xmlpoke-task.md)  
 Nastaví hodnoty podle specifikace dotaz XPath do souboru XML.  
  
 [XslTransformation – úloha](../msbuild/xsltransformation-task.md)  
 Transformuje vstup XML pomocí *rozšiřitelný jazyk transformace šablony stylů* (XSLT) nebo zkompilovat XSLT a výstupy do výstupní zařízení nebo souboru.  
  
## <a name="see-also"></a>Viz také  
 [MSBuild – Reference](../msbuild/msbuild-reference.md)   
 [Zápis úloh](../msbuild/task-writing.md)   
 [Úlohy](../msbuild/msbuild-tasks.md)