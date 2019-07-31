---
title: Společné položky projektu nástroje MSBuild | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, common project items
ms.assetid: 1eba3721-cc12-4b80-9987-84923ede5e2e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 1271752a32a2f42eca93ae3f6861a923a6055cd2
ms.sourcegitcommit: 5694c5236fa32ba7f5bc1236a853f725ec7557e9
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 07/31/2019
ms.locfileid: "68681283"
---
# <a name="common-msbuild-project-items"></a>Společné položky projektu nástroje MSBuild
V [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]je položka pojmenovaný odkaz na jeden nebo více souborů. Položky obsahují metadata, jako jsou názvy souborů, cesty a čísla verzí. Všechny typy projektů v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] aplikaci mají několik společných položek. Tyto položky jsou definovány v souboru *Microsoft. Build. CommonTypes. xsd*.

## <a name="common-items"></a>Společné položky
 Níže je seznam všech běžných položek projektu.

### <a name="reference"></a>Reference
 Představuje odkaz sestavení (spravovaného) v projektu.

|Název metadat položky|Popis|
|---------------|-----------------|
|HintPath|Volitelný řetězec. Relativní nebo absolutní cesta k sestavení|
|Name|Volitelný řetězec. Zobrazovaný název sestavení, například "System. Windows. Forms."|
|Fusion|Volitelný řetězec. Určuje jednoduchý nebo silný název fúze pro položku.<br /><br /> Pokud je tento atribut přítomen, může ušetřit čas, protože soubor sestavení není nutné otevřít, aby získal název fúze.|
|SpecificVersion|Volitelná logická hodnota. Určuje, zda má být odkazována pouze verze v názvu fúze.|
|Aliasy|Volitelný řetězec. Všechny aliasy pro referenci|
|Soukromé|Volitelná logická hodnota. Určuje, zda má být odkaz zkopírován do výstupní složky. Tento atribut odpovídá vlastnosti **Copy Local** odkazu, který je v integrovaném vývojovém prostředí sady Visual Studio.|

### <a name="comreference"></a>COMReference
 Představuje odkaz na komponentu modelu COM (nespravovaný) v projektu. Tato položka se vztahuje pouze na projekty .NET.

|Název metadat položky|Popis|
|---------------|-----------------|
|Name|Volitelný řetězec. Zobrazovaný název součásti.|
|Guid|Povinný řetězec. Identifikátor GUID pro komponentu ve formuláři {12345678-1234-1234-1234-1234567891234}.|
|VersionMajor|Povinný řetězec. Hlavní část čísla verze součásti. Například "5", pokud je číslo úplné verze "5,46".|
|VersionMinor|Povinný řetězec. Vedlejší část čísla verze součásti. Například "46", pokud je číslo úplné verze "5,46".|
|IDENTIFIKÁTORY|Volitelný řetězec. LocaleID pro komponentu|
|WrapperTool|Volitelný řetězec. Název nástroje obálky, který se používá pro komponentu, například "Tlbimp".|
|Izolován|Volitelná logická hodnota. Určuje, zda je komponenta komponentou bez registrace.|

### <a name="comfilereference"></a>COMFileReference
 Představuje seznam knihoven typů, které jsou předány `TypeLibFiles` parametru cíle [ResolveComReference –](resolvecomreference-task.md) . Tato položka se vztahuje pouze na projekty .NET.

|Název metadat položky|Popis|
|---------------|-----------------|
|WrapperTool|Volitelný řetězec. Název nástroje obálky, který se používá pro komponentu, například "Tlbimp".|

### <a name="nativereference"></a>NativeReference
 Představuje nativní soubor manifestu nebo odkaz na takový soubor.

|Název metadat položky|Popis|
|---------------|-----------------|
|Name|Povinný řetězec. Základní název souboru manifestu.|
|HintPath|Povinný řetězec. Relativní cesta k souboru manifestu.|

### <a name="projectreference"></a>ProjectReference
 Představuje odkaz na jiný projekt.

|Název metadat položky|Popis|
|---------------|-----------------|
|Name|Volitelný řetězec. Zobrazovaný název odkazu|
|Project|Volitelný řetězec. Identifikátor GUID odkazu ve formuláři {12345678-1234-1234-1234-1234567891234}.|
|Balíček|Volitelný řetězec. Cesta k souboru projektu, na který se odkazuje|
|ReferenceOutputAssembly|Volitelná logická hodnota. Pokud je nastaveno `false`na, nezahrnuje výstup odkazovaného projektu jako [odkaz](#reference) na tento projekt, ale stále zajišťuje, aby druhý projekt sestavil před tímto prvkem. Výchozí hodnota je `true`.|

### <a name="compile"></a>Kompilace
 Představuje zdrojové soubory pro kompilátor.

| Název metadat položky | Popis |
|-----------------------| - |
| DependentUpon | Volitelný řetězec. Určuje soubor, na kterém je tento soubor závislý, aby se správně zkompiluje. |
| AutoGen | Volitelná logická hodnota. Označuje, zda byl soubor generován pro projekt pomocí [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrovaného vývojového prostředí (IDE). |
| Odkaz | Volitelný řetězec. Cesta k zápisu, která se má zobrazit, pokud je soubor fyzicky umístěný mimo vliv souboru projektu. |
| Viditelné | Volitelná logická hodnota. Určuje, zda se má soubor zobrazit v Průzkumník řešení [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]v. |
| CopyToOutputDirectory | Volitelný řetězec. Určuje, zda se má soubor zkopírovat do výstupního adresáře. Hodnoty jsou:<br /><br /> 1.  Nikdy<br />2.  Vždy<br />3.  PreserveNewest |

### <a name="embeddedresource"></a>EmbeddedResource
 Představuje prostředky, které mají být vloženy do generovaného sestavení.

| Název metadat položky | Popis |
|-----------------------| - |
| DependentUpon | Volitelný řetězec. Určuje soubor, na kterém je tento soubor závislý, aby se správně zkompiluje. |
| Generátor | Povinný řetězec. Název jakéhokoli generátoru souborů, který je spuštěn na této položce. |
| LastGenOutput | Povinný řetězec. Název souboru, který byl vytvořen generátorem souborů, který u této položky běžel. |
| CustomToolNamespace | Povinný řetězec. Obor názvů, ve kterém má každý generátor souborů, který běží na této položce, vytvořit kód. |
| Odkaz | Volitelný řetězec. Cesta k zápisu se zobrazí, pokud je soubor fyzicky umístěný mimo vliv projektu. |
| Viditelné | Volitelná logická hodnota. Určuje, zda se má soubor zobrazit v Průzkumník řešení [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]v. |
| CopyToOutputDirectory | Volitelný řetězec. Určuje, zda se má soubor zkopírovat do výstupního adresáře. Hodnoty jsou:<br /><br /> 1.  Nikdy<br />2.  Vždy<br />3.  PreserveNewest |
| Logický operátor | Povinný řetězec. Logický název vloženého prostředku. |

### <a name="content"></a>Obsah
 Představuje soubory, které nejsou zkompilovány do projektu, ale mohou být vloženy nebo publikovány společně s ní.

| Název metadat položky | Popis |
|-----------------------| - |
| DependentUpon | Volitelný řetězec. Určuje soubor, na kterém je tento soubor závislý, aby se správně zkompiluje. |
| Generátor | Povinný řetězec. Název jakéhokoli generátoru souborů, který se na této položce spouští. |
| LastGenOutput | Povinný řetězec. Název souboru, který byl vytvořen generátorem souborů spuštěným u této položky. |
| CustomToolNamespace | Povinný řetězec. Obor názvů, ve kterém má každý generátor souborů, který běží na této položce, vytvořit kód. |
| Odkaz | Volitelný řetězec. Cesta k zápisu, která se má zobrazit, pokud je soubor fyzicky umístěný mimo vliv projektu. |
| PublishState | Povinný řetězec. Stav publikování obsahu, a to buď:<br /><br /> – Výchozí<br />– Zahrnuto<br />– Vyloučené<br />– Datový datový<br />– Předpoklad |
| Sestavení | Volitelná logická hodnota. Určuje, zda je soubor sestavením. |
| Viditelné | Volitelná logická hodnota. Určuje, zda se má soubor zobrazit v Průzkumník řešení [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]v. |
| CopyToOutputDirectory | Volitelný řetězec. Určuje, zda se má soubor zkopírovat do výstupního adresáře. Hodnoty jsou:<br /><br /> 1.  Nikdy<br />2.  Vždy<br />3.  PreserveNewest |

### <a name="none"></a>Žádné
 Představuje soubory, které by neměly mít žádné role v procesu sestavení.

| Název metadat položky | Popis |
|-----------------------| - |
| DependentUpon | Volitelný řetězec. Určuje soubor, na kterém je tento soubor závislý, aby se správně zkompiluje. |
| Generátor | Povinný řetězec. Název jakéhokoli generátoru souborů, který je spuštěn na této položce. |
| LastGenOutput | Povinný řetězec. Název souboru, který byl vytvořen generátorem souborů, který u této položky běžel. |
| CustomToolNamespace | Povinný řetězec. Obor názvů, ve kterém má každý generátor souborů, který běží na této položce, vytvořit kód. |
| Odkaz | Volitelný řetězec. Cesta k zápisu, která se má zobrazit, pokud je soubor fyzicky umístěný mimo vliv projektu. |
| Viditelné | Volitelná logická hodnota. Určuje, zda se má soubor zobrazit v Průzkumník řešení [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]v. |
| CopyToOutputDirectory | Volitelný řetězec. Určuje, zda se má soubor zkopírovat do výstupního adresáře. Hodnoty jsou:<br /><br /> 1.  Nikdy<br />2.  Vždy<br />3.  PreserveNewest |

### <a name="baseapplicationmanifest"></a>BaseApplicationManifest
 Představuje manifest základní aplikace pro sestavení a obsahuje [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] informace o zabezpečení nasazení.

### <a name="codeanalysisimport"></a>CodeAnalysisImport
 Představuje projekt FxCop, který se má importovat.

### <a name="import"></a>Import
 Představuje sestavení, jejichž obory názvů by měly [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] být importovány kompilátorem.

## <a name="see-also"></a>Viz také:
- [Obecné vlastnosti projektu nástroje MSBuild](../msbuild/common-msbuild-project-properties.md)
