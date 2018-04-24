---
title: Generatedeploymentmanifest – úloha | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#GenerateDeploymentManifest
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, GenerateDeploymentManifest task
- GenerateDeploymentManifest task [MSBuild]
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a1eb989972f8cfd2e44516b798c25e5f579e5f66
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
---
# <a name="generatedeploymentmanifest-task"></a>GenerateDeploymentManifest – úloha

Generuje [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] – manifest nasazení. A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] – manifest nasazení popisuje nasazení aplikace tak, že definujete jedinečnou identitu pro nasazení, identifikace vlastnosti nasazení, jako je instalace nebo online režimu, zadání aplikace aktualizovat nastavení a je nutné aktualizovat umístění, a označující odpovídající [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace.

## <a name="parameters"></a>Parametry

Následující tabulka popisuje parametry `GenerateDeploymentManifest` úloh.

|Parametr|Popis|
|---------------|-----------------|
|`AssemblyName`|Volitelné `String` parametr.<br /><br /> Určuje, `Name` pole identity sestavení pro vygenerovaný manifest. Pokud není tento parametr zadán, je název odvodit z `EntryPoint` nebo `InputManifest` parametry. Pokud název nelze odvodit, úloha vrátí chybu.|
|`AssemblyVersion`|Volitelné `String` parametr.<br /><br /> Určuje, `Version` pole identity sestavení pro vygenerovaný manifest. Pokud není tento parametr zadán, použije úloha hodnotu "1.0.0.0".|
|`CreateDesktopShortcut`|Volitelné `Boolean` parametr.<br /><br /> V případě hodnoty true je vytvořen ikony na ploše během instalace aplikace ClickOnce.|
|`DeploymentUrl`|Volitelné `String` parametr.<br /><br /> Určuje umístění aktualizace pro aplikaci. Pokud není tento parametr zadán, pro aplikaci není definován žádný umístění aktualizace. Ale pokud `UpdateEnabled` parametr `true`, musí být zadané umístění aktualizace. Zadaná hodnota by měla být plně kvalifikovanou cestu adresy URL nebo cestu UNC.|
|`Description`|Volitelné `String` parametr.<br /><br /> Určuje popis aplikace.|
|`DisallowUrlActivation`|Volitelné `Boolean` parametr.<br /><br /> Určuje, jestli by měl být aplikace spustit automaticky při otevření prostřednictvím adresy URL. Pokud tento parametr je `true`, aplikaci lze spustit pouze z nabídky Start. Výchozí hodnota tohoto parametru je `false`. Tento vstup platí pouze tehdy, když `Install` je hodnota parametru `true`.|
|`EntryPoint`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr.<br /><br /> Určuje vstupní bod pro vygenerovaný manifest sestavení. Pro [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest nasazení, určuje tento vstup [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] manifest aplikace.<br /><br />Pokud `EntryPoint` není zadán parametr úloh, `<customHostSpecified>` značky je vložit jako podřízený `<entryPoint>` značka, například:<br /><br /> `<entryPoint xmlns="urn:schemas-`<br /><br /> `microsoft-com:asm.v2">`<br /><br /> `<co.v1:customHostSpecified />`<br /><br /> `</entryPoint>`<br /><br /> Knihovny DLL závislosti můžete přidat do manifestu aplikace pomocí následujících kroků:<br /><br /> 1.  Vyřešte reference sestavení pomocí volání <xref:Microsoft.Build.Tasks.ResolveAssemblyReference>.<br />2.  Předat výstup předchozí úloha a samotného sestavení do <xref:Microsoft.Build.Tasks.ResolveManifestFiles>.<br />3.  Předat závislosti pomocí `Dependencies` parametru <xref:Microsoft.Build.Tasks.GenerateApplicationManifest>.|
|`ErrorReportUrl`|Volitelné <xref:System.String?displayProperty=fullName> parametr.<br /><br /> Určuje adresu URL webové stránky, která se zobrazí v dialogových oknech během instalace ClickOnce.|
|`InputManifest`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje vstupní dokument XML sloužit jako základ pro generátor manifestu. To umožňuje strukturovaných dat, jako jsou vlastní manifestu definice projeví v manifestu výstup. Kořenový element v dokumentu XML musí být do uzlu sestavení v oboru názvů asmv1.|
|`Install`|Volitelné `Boolean` parametr.<br /><br /> Určuje, zda je aplikace nainstalovaná aplikace nebo aplikaci pouze online. Pokud tento parametr je `true`, aplikace bude nainstalována na uživatele nabídky Start a lze odebrat pomocí dialogu přidat nebo odebrat programy. Pokud tento parametr je `false`, aplikace je určená pro online z webové stránky. Výchozí hodnota tohoto parametru je `true`.|
|`MapFileExtensions`|Volitelné `Boolean` parametr.<br /><br /> Určuje, jestli se používá mapování přípon názvů souborů .deploy. Pokud tento parametr je `true`, každý soubor programu je publikována s příponu názvu souboru .deploy. Tato možnost je užitečná pro zabezpečení webového serveru a omezit počet přípony názvů souborů, které musí se odblokovat povolit [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení aplikace. Výchozí hodnota tohoto parametru je `false`.|
|`MaxTargetPath`|Volitelné `String` parametr.<br /><br /> Určuje maximální povolená délka cesty k souboru v [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] nasazení aplikace. Pokud je tento parametr zadán, je tento limit kontrolovat délka cesty každý soubor v aplikaci. Upozornění sestavení způsobí, že všechny položky, které překračují limit. Pokud tento vstup není zadána nebo rovná nule, se neprovádí žádné kontrola.|
|`MinimumRequiredVersion`|Volitelné `String` parametr.<br /><br /> Určuje, jestli uživatel může aktualizace bude přeskočena. Pokud má uživatel na verzi, která je menší než požadované minimum, že nebude mít možnost aktualizace bude přeskočena. Tento vstup pouze pokud platí hodnota `Install` parametr `true`.|
|`OutputManifest`|Volitelné <xref:Microsoft.Build.Framework.ITaskItem> parametr.<br /><br /> Určuje název souboru manifestu generovaný výstup. Pokud není tento parametr zadán, je název souboru výstupního souboru odvodit z identity vygenerovaný manifest.|
|`Platform`|Volitelné `String` parametr.<br /><br /> Určuje cílovou platformu aplikace. Tento parametr může mít následující hodnoty:<br /><br /> -   `AnyCPU`<br />-   `x86`<br />-   `x64`<br />-   `Itanium`<br /><br /> Výchozí hodnota je `AnyCPU`.|
|`Product`|Volitelné `String` parametr.<br /><br /> Určuje název aplikace. Pokud není tento parametr zadán, je název odvodit z identity vygenerovaný manifest. Tento název se používá pro název místní nabídky Start a je součástí názvu, který se zobrazí v dialogovém okně Přidat nebo odebrat programy.|
|`Publisher`|Volitelné `String` parametr.<br /><br /> Určuje vydavatele aplikace. Pokud není tento parametr zadán, je název odvodit z registrovaní uživatelé, nebo identitu vygenerovaný manifest. Tento název se používá pro název složky v nabídce Start a je součástí názvu, který se zobrazí v dialogovém okně Přidat nebo odebrat programy.|
|`SuiteNamel`|Volitelné `String` parametr.<br /><br /> Určuje název složky v nabídce Start, kde se nachází aplikace po nasazení ClickOnce.|
|`SupportUrl`|Volitelné `String` parametr.<br /><br /> Určuje odkaz, který se zobrazí v dialogovém okně Přidat nebo odebrat programy pro aplikaci. Zadaná hodnota by měla být plně kvalifikovanou cestu adresy URL nebo cestu UNC.|
|`TargetCulture`|Volitelné `String` parametr.<br /><br /> Identifikuje jazykové verze aplikace a určuje, `Language` pole identity sestavení pro vygenerovaný manifest. Pokud není tento parametr zadán, předpokládá se, že aplikace je neutrální jazykovou verzi.|
|`TrustUrlParameters`|Volitelné `Boolean` parametr.<br /><br /> Určuje, zda parametrů řetězce dotazu adresy URL má k dispozici pro aplikaci. Výchozí hodnota tohoto parametru je `false`, což naznačuje, že parametry nebudou k dispozici na aplikaci.|
|`UpdateEnabled`|Volitelné `Boolean` parametr.<br /><br /> Určuje, zda aplikace povolena pro aktualizace. Výchozí hodnota tohoto parametru je `false`. Tento parametr se vztahuje pouze při hodnotu `Install` parametr `true`.|
|`UpdateInterval`|Volitelné `Int32` parametr.<br /><br /> Určuje interval aktualizace pro aplikaci. Výchozí hodnota tohoto parametru je nula. Tento parametr se vztahuje pouze pokud hodnoty `Install` a `UpdateEnabled` parametry jsou obě `true`.|
|`UpdateMode`|Volitelné `String` parametr.<br /><br /> Určuje, zda aktualizace je třeba kontrolovat na popředí, předtím, než aplikace spuštěný, nebo na pozadí jako aplikace běží. Tento parametr může mít následující hodnoty:<br /><br /> -   `Foreground`<br />-   `Background`<br /><br /> Výchozí hodnota tohoto parametru je `Background`. Tento parametr se vztahuje pouze pokud hodnoty `Install` a `UpdateEnabled` parametry jsou obě `true`.|
|`UpdateUnit`|Volitelné `String` parametr.<br /><br /> Určuje, že jednotky `UpdateInterval` parametr. Tento parametr může mít následující hodnoty:<br /><br /> -   `Hours`<br />-   `Days`<br />-   `Weeks`<br /><br /> Tento parametr se vztahuje pouze pokud hodnoty `Install` a `UpdateEnabled` parametry jsou obě `true`.|

## <a name="remarks"></a>Poznámky

Kromě výše uvedených parametrů tato úloha dědí parametry z <xref:Microsoft.Build.Tasks.GenerateManifestBase> třída, které dědí z <xref:Microsoft.Build.Utilities.Task> třídy. Seznam parametrů třída úlohy najdete v tématu [Třída Base úlohy](../msbuild/task-base-class.md).

## <a name="see-also"></a>Viz také

[Úlohy](../msbuild/msbuild-tasks.md)  
[GenerateApplicationManifest – úloha](../msbuild/generateapplicationmanifest-task.md)  
[SignFile – úloha](../msbuild/signfile-task.md)  
[Referenční dokumentace úlohy](../msbuild/msbuild-task-reference.md)