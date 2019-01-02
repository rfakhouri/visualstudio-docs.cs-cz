---
title: Nástroj MSBuild vyhrazené a známé vlastnosti | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, reserved properties
ms.assetid: 99333e61-83c9-4804-84e3-eda297c2478d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 82ab1ec887fd6a0c881f2d1e4b0c1295e1c67716
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53967732"
---
# <a name="msbuild-reserved-and-well-known-properties"></a>Nástroj MSBuild vyhrazené a dobře známé vlastnosti
[!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] poskytuje sadu předdefinovaných vlastností, které ukládají informace o souboru projektu a [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] binární soubory. Tyto vlastnosti jsou vyhodnocovány stejným způsobem jako ostatní [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] vlastnosti. Chcete-li například použít `MSBuildProjectFile` vlastnost, typ `$(MSBuildProjectFile)`.  

 Nástroj MSBuild používá hodnoty v následující tabulce pro předdefinování rezervovaných a dobře známých vlastností. Rezervované vlastnosti nemohou být potlačeny, ale dobře známé vlastnosti lze přepsat pomocí nazvanými vlastnostmi prostředí, globálními vlastnostmi nebo vlastnostmi, které jsou deklarovány v souboru projektu.

## <a name="reserved-and-well-known-properties"></a>Vyhrazené a dobře známé vlastnosti  
 V následující tabulce jsou popsány [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] předdefinované vlastnosti.  


| Vlastnost | Vyhrazené nebo známé | Popis |
|----------------------------------|------------------------| - |
| `MSBuildBinPath` | Vyhrazeno | Absolutní cesta ke složce kde [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] jsou umístěny binární soubory, které jsou právě používány (například *C:\Windows\Microsoft.Net\Framework\\\<číslo_verze >*). Tato vlastnost je užitečná, pokud máte k odkazování na soubory v [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] adresáře.<br /><br /> Nezahrnují konečné zpětné lomítko pro tuto vlastnost. |
| `MSBuildExtensionsPath` | Známé | Zavedena v rozhraní .NET Framework 4: není žádný rozdíl mezi výchozími hodnotami `MSBuildExtensionsPath` a `MSBuildExtensionsPath32`. Můžete nastavit proměnné prostředí `MSBUILDLEGACYEXTENSIONSPATH` na nenulovou hodnotu, chcete-li povolit chování výchozí hodnoty `MSBuildExtensionsPath` v dřívějších verzích.<br /><br /> V rozhraní .NET Framework 3.5 a starších, výchozí hodnota `MSBuildExtensionsPath` odkazuje na cestu podsložky MSBuild ve složce *\Program Files\\*  nebo *\Program Files (x86)* složce v závislosti na počtu bitů aktuálního procesu. Například pro 32bitový proces na 64bitovém počítači, tato vlastnost odkazuje na *\Program Files (x86)* složky. Pro 64bitový proces na 64bitovém počítači, tato vlastnost odkazuje na *\Program Files* složky.<br /><br /> Nezahrnují konečné zpětné lomítko pro tuto vlastnost.<br /><br /> Toto umístění je vhodné místo pro vlastní cílové soubory. Například cílové soubory mohl nainstalovat na *\Program Files\MSBuild\MyFiles\Northwind.targets* a následně importovány do projektových souborů pomocí tohoto kódu XML:<br /><br /> `<Import Project="$(MSBuildExtensionsPath)\MyFiles\Northwind.targets"/>` |
| `MSBuildExtensionsPath32` | Známé | Cesta [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] podsložku *\Program Files* nebo *\Program Files (x86)* složky. Cesta vždy odkazuje na 32bitovou verzi *\Program Files (x86)* složky na 32bitovém počítači a *\Program Files* na 64bitovém počítači. ". Viz také `MSBuildExtensionsPath` a `MSBuildExtensionsPath64`.<br /><br /> Nezahrnují konečné zpětné lomítko pro tuto vlastnost. |
| `MSBuildExtensionsPath64` | Známé | Cesta [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] podsložku *\Program Files* složky. Pro 64bitový počítač tato cesta vždy odkazuje na *\Program Files* složky. Pro 32bitový počítač tato cesta je prázdná. Viz také `MSBuildExtensionsPath` a `MSBuildExtensionsPath32`.<br /><br /> Nezahrnují konečné zpětné lomítko pro tuto vlastnost. |
| `MSBuildLastTaskResult` | Vyhrazeno | `true` Pokud byl předchozí úkol dokončen bez chyb (i kdyby to byla upozornění), nebo `false` Pokud předchozí úloha obsahovala chyby. Obvykle když dojde k chybě v úloze, chyba je poslední věcí, ke které dochází v daném projektu. Hodnota této vlastnosti tedy nikdy `false`, s výjimkou v těchto scénářích:<br /><br /> – Když `ContinueOnError` atribut [Task – element (MSBuild)](../msbuild/task-element-msbuild.md) je nastavena na `WarnAndContinue` (nebo `true`) nebo `ErrorAndContinue`.<br /><br /> – Když `Target` má [onerror – element (MSBuild)](../msbuild/onerror-element-msbuild.md) jako podřízený prvek. |
| `MSBuildNodeCount` | Vyhrazeno | Maximální počet souběžných procesů, které se používají při sestavování. Jedná se o hodnotu, která jste zadali pro **- maxcpucount** na příkazovém řádku. Pokud jste zadali **- maxcpucount** bez zadání hodnoty, pak `MSBuildNodeCount` určuje počet procesorů v počítači. Další informace najdete v tématu [odkaz na příkazový řádek](../msbuild/msbuild-command-line-reference.md) a [sestavování více projektů současně](../msbuild/building-multiple-projects-in-parallel-with-msbuild.md). |
| `MSBuildProgramFiles32` | Vyhrazeno | Umístění složky 32bitových programů; například *C:\Program Files (x86)*.<br /><br /> Nezahrnují konečné zpětné lomítko pro tuto vlastnost. |
| `MSBuildProjectDefaultTargets` | Vyhrazeno | Úplný seznam cílů, které jsou určené v `DefaultTargets` atribut `Project` elementu. Například následující `Project` element bude mít `MSBuildDefaultTargets` hodnotou vlastnosti `A;B;C`:<br /><br /> `<Project DefaultTargets="A;B;C" >` |
| `MSBuildProjectDirectory` | Vyhrazeno | Absolutní cesta adresáře, kde je soubor projektu umístěn, například *C:\MyCompany\MyProduct*.<br /><br /> Nezahrnují konečné zpětné lomítko pro tuto vlastnost. |
| `MSBuildProjectDirectoryNoRoot` | Vyhrazeno | Hodnota `MSBuildProjectDirectory` vlastnost, s výjimkou kořenové jednotky.<br /><br /> Nezahrnují konečné zpětné lomítko pro tuto vlastnost. |
| `MSBuildProjectExtension` | Vyhrazeno | Příponu názvu souboru projektu, včetně tečky; například *souborů .proj*. |
| `MSBuildProjectFile` | Vyhrazeno | Celý název souboru projektu, včetně přípony názvu souboru; například *MyApp.proj*. |
| `MSBuildProjectFullPath` | Vyhrazeno | Absolutní cesta a celý název souboru projektu, včetně přípony názvu souboru; například *C:\MyCompany\MyProduct\MyApp.proj*. |
| `MSBuildProjectName` | Vyhrazeno | Název souboru bez přípony názvu souboru; v souboru projektu například *MyApp*. |
| `MSBuildRuntimeType` | Vyhrazeno | Typ modulu runtime, který aktuálně spouští. Zavedená v nástroji MSBuild 15. Hodnota může nedefinovaný (před MSBuild 15) `Full` označující, že nástroj MSBuild běží na klasické pracovní plochy rozhraní .NET Framework, `Core` označující, že nástroj MSBuild je spuštěn v rozhraní .NET Core nebo `Mono` označující, že nástroj MSBuild je spuštěn na Mono. |
| `MSBuildStartupDirectory` | Vyhrazeno | Absolutní cesta ke složce kde [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] je volána. Pomocí této vlastnosti můžete sestavit vše pod určitým bodem ve stromu projektu bez vytváření  *\<adresáře > souborů .proj* soubory v každém adresáři. Místo toho máte pouze jeden projekt, například *c:\traversal.proj*, jak je znázorněno zde:<br /><br /> `<Project ...>     <ItemGroup>         <ProjectFiles              Include="$            (MSBuildStartupDirectory)            **\*.csproj"/>     </ItemGroup>     <Target Name="build">         <MSBuild             Projects="@(ProjectFiles)"/>     </Target> </Project>`<br /><br /> Pokud chcete sestavit jakýkoli bod ve stromové struktuře, zadejte:<br /><br /> `msbuild c:\traversal.proj`<br /><br /> Nezahrnují konečné zpětné lomítko pro tuto vlastnost. |
| `MSBuildThisFile` | Vyhrazeno | Název souboru a část přípony souboru `MSBuildThisFileFullPath`. |
| `MSBuildThisFileDirectory` | Vyhrazeno | Část adresáře `MSBuildThisFileFullPath`.<br /><br /> Zahrňte v cestě konečné zpětné lomítko. |
| `MSBuildThisFileDirectoryNoRoot` | Vyhrazeno | Část adresáře `MSBuildThisFileFullPath`, s výjimkou kořenové jednotky.<br /><br /> Zahrňte v cestě konečné zpětné lomítko. |
| `MSBuildThisFileExtension` | Vyhrazeno | Část přípony názvu souboru z `MSBuildThisFileFullPath`. |
| `MSBuildThisFileFullPath` | Vyhrazeno | Absolutní cesta souboru projektu nebo cílů, který obsahuje cíl, na kterém běží.<br /><br /> Tip: Můžete použít relativní cestu v souboru cílů, která je relativní vzhledem k souboru cílů a ne vzhledem k původnímu souboru projektu. |
| `MSBuildThisFileName` | Vyhrazeno | Část názvu souboru `MSBuildThisFileFullPath`, bez přípony názvu souboru. |
| `MSBuildToolsPath` | Vyhrazeno | Instalační cesta [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] verzi, která je přidružená hodnota `MSBuildToolsVersion`.<br /><br /> Nezahrnují v cestě konečné zpětné lomítko.<br /><br /> Tuto vlastnost nelze přepsat. |
| `MSBuildToolsVersion` | Vyhrazeno | Verze [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] nástrojů, která se používá k sestavení projektu.<br /><br /> Poznámka: [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] Sada nástrojů obsahuje úkoly, cíle a nástroje, které slouží k sestavení aplikace. Mezi tyto nástroje patří kompilátory jako *csc.exe* a *vbc.exe*. Další informace najdete v tématu [sada nástrojů (atribut ToolsVersion)](../msbuild/msbuild-toolset-toolsversion.md), a [standardní a vlastní konfigurace sady nástrojů](../msbuild/standard-and-custom-toolset-configurations.md). |

## <a name="names-that-conflict-with-msbuild-elements"></a>Názvy, které jsou v konfliktu s elementy MSBuild

Kromě výše uvedeného pojmenuje odpovídající jazykové prvky nelze použít pro uživatelem definované vlastnosti, položky nebo metadata položky nástroje MSBuild:

* VisualStudioProject
* Target
* PropertyGroup
* Výstup
* ItemGroup
* Usingtask –
* Projectextensions –
* Onerror –
* Importgroup –
* Zvolte
* Kdy
* jinak

## <a name="see-also"></a>Viz také:  
[Referenční dokumentace nástroje MSBuild](../msbuild/msbuild-reference.md)

[Vlastnosti nástroje MSBuild](../msbuild/msbuild-properties.md)
