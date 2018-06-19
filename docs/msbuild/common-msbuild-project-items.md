---
title: Běžné projektu nástroje MSBuild položky | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
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
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 46ea8c1ffd52805be4f93fb59c2831f5f0fe610c
ms.sourcegitcommit: 42ea834b446ac65c679fa1043f853bea5f1c9c95
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/19/2018
ms.locfileid: "31574256"
---
# <a name="common-msbuild-project-items"></a>Společné položky projektu nástroje MSBuild
V [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)], je určitá položka s názvem odkaz na jeden nebo více souborů. Položky obsahovat metadata, jako jsou názvy souborů, cesty a čísel verzí. Všechny typy v projektu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] mají společnou několik položek. Tyto položky jsou definovány v souboru Microsoft.Build.CommonTypes.xsd.  
  
## <a name="common-items"></a>Společné položky  
 Následuje seznam všech společné položky projektu.  
  
### <a name="reference"></a>Odkaz  
 Představuje odkaz na sestavení (spravované) v projektu.  
  
|Název položky metadat|Popis|  
|---------------|-----------------|  
|HintPath|Volitelný řetězec. Relativní nebo absolutní cesta sestavení.|  
|Název|Volitelný řetězec. Zobrazovaný název sestavení, například "System.Windows.Forms."|  
|FusionName|Volitelný řetězec. Určuje název jednoduchý nebo silné fusion pro položku.<br /><br /> Když tento atribut je k dispozici, můžete ušetřit čas, protože nebude muset otevřít získat fusion název souboru sestavení.|  
|SpecificVersion|Volitelné logická hodnota. Určuje, zda by měl odkazovat jenom verze v názvu fusion.|  
|Aliasy|Volitelný řetězec. Pro odkaz na všechny aliasy.|  
|Soukromé|Volitelné logická hodnota. Určuje, zda by měl odkaz zkopírován do výstupní složky. Tento atribut odpovídá **místní kopie** vlastnost odkazu, který je v prostředí Visual Studio IDE.|  
  
### <a name="comreference"></a>COMReference  
 Představuje komponenty modelu COM (nespravovaný) odkazovat v projektu.  
  
|Název položky metadat|Popis|  
|---------------|-----------------|  
|Název|Volitelný řetězec. Zobrazovaný název součásti.|  
|Identifikátor GUID|Volitelný řetězec. Identifikátor GUID pro komponentu ve formuláři {12345678-1234-1234-1234-1234567891234}.|  
|VersionMajor|Volitelný řetězec. Část hlavní číslo verze součásti. Například "5" Pokud je číslo plnou verzi "5.46."|  
|VersionMinor|Volitelný řetězec. Menší část číslo verze součásti. Například "46" Pokud je číslo plnou verzi "5.46."|  
|LCID|Volitelný řetězec. Identifikátor národního prostředí pro komponentu.|  
|WrapperTool|Volitelný řetězec. Název obálku nástroj, který se používá na komponentu, například "tlbimp."|  
|Izolované|Volitelné logická hodnota. Určuje, jestli je součást komponentu bez registrace.|  
  
### <a name="comfilereference"></a>COMFileReference  
 Představuje seznam knihovny typů, které informačního kanálu do cílové ResolvedComreference.  
  
|Název položky metadat|Popis|  
|---------------|-----------------|  
|WrapperTool|Volitelný řetězec. Název obálku nástroj, který se používá na komponentu, například "tlbimp."|  
  
### <a name="nativereference"></a>NativeReference  
 Představuje soubor manifestu nativní nebo odkaz na takový soubor.  
  
|Název položky metadat|Popis|  
|---------------|-----------------|  
|Název|Požadovaný řetězec. Základní název souboru manifestu.|  
|HintPath|Požadovaný řetězec. Relativní cesta souboru manifestu.|  
  
### <a name="projectreference"></a>ProjectReference  
 Představuje odkaz na jiný projekt.  
  
|Název položky metadat|Popis|  
|---------------|-----------------|  
|Název|Volitelný řetězec. Zobrazovaný název odkazu.|  
|Projekt|Volitelný řetězec. Identifikátor GUID pro odkaz na ve formuláři {12345678-1234-1234-1234-1234567891234}.|  
|Balíček|Volitelný řetězec. Cesta souboru projektu, který je odkazováno.|  
  
### <a name="compile"></a>Kompilace  
 Představuje zdrojové soubory pro kompilátor.  
  
|Název položky metadat|Popis|  
|---------------|-----------------|  
|DependentUpon|Volitelný řetězec. Určuje soubor, který tento soubor závisí na pro správnou kompilaci.|  
|AutoGen|Volitelné logická hodnota. Určuje, zda soubor byl vygenerován pro do projektu [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] integrované vývojové prostředí (IDE).|  
|Odkaz|Volitelný řetězec. Konvenční cesta k zobrazí, když se soubor nachází fyzicky mimo vlivu souboru projektu.|  
|Viditelné|Volitelné logická hodnota. Označuje, zda zobrazit soubor v **Průzkumníku řešení** v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|CopyToOutputDirectory|Volitelný řetězec. Určuje, zda při kopírování souboru do výstupního adresáře. Hodnoty jsou:<br /><br /> 1.  Nikdy<br />2.  Vždy<br />3.  PreserveNewest|  
  
### <a name="embeddedresource"></a>EmbeddedResource  
 Představuje prostředky, které má být vložen v generovaném sestavení.  
  
|Název položky metadat|Popis|  
|---------------|-----------------|  
|DependentUpon|Volitelný řetězec. Určuje soubor, který tento soubor závisí na pro správnou kompilaci|  
|Generátor|Požadovaný řetězec. Název generátor všech souborů, který se spouští na tuto položku.|  
|LastGenOutput|Požadovaný řetězec. Název souboru, který byl vytvořen generátor všech souborů, který byl spuštěn na tuto položku.|  
|CustomToolNamespace|Požadovaný řetězec. Kód by měl vytvořit obor názvů, ve které žádný soubor generátor, který běží na tuto položku.|  
|Odkaz|Volitelný řetězec. Konvenční cesta se zobrazí, pokud se soubor nachází fyzicky mimo vliv projektu.|  
|Viditelné|Volitelné logická hodnota. Označuje, zda zobrazit soubor v **Průzkumníku řešení** v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|CopyToOutputDirectory|Volitelný řetězec. Určuje, zda při kopírování souboru do výstupního adresáře. Hodnoty jsou:<br /><br /> 1.  Nikdy<br />2.  Vždy<br />3.  PreserveNewest|  
|LogicalName|Požadovaný řetězec. Logický název vložený prostředek.|  
  
### <a name="content"></a>Obsah  
 Představuje soubory, které nejsou zkompilovány do projektu, ale může vložených nebo publikované společně s ho.  
  
|Název položky metadat|Popis|  
|---------------|-----------------|  
|DependentUpon|Volitelný řetězec. Určuje soubor, který tento soubor závisí na pro správnou kompilaci.|  
|Generátor|Požadovaný řetězec. Název generátor všech souborů, která běží na tuto položku.|  
|LastGenOutput|Požadovaný řetězec. Název souboru, který byl vytvořen žádné Generátor souborů, která byla spuštěna na této položce.|  
|CustomToolNamespace|Požadovaný řetězec. Kód by měl vytvořit obor názvů, ve které žádný soubor generátor, který běží na tuto položku.|  
|Odkaz|Volitelný řetězec. Konvenční cesta, který se má zobrazit, pokud se soubor nachází fyzicky mimo vliv projektu.|  
|PublishState|Požadovaný řetězec. Stav publikování obsahu, buď:<br /><br /> -Výchozí<br />-Zahrnuté<br />-Vyloučit<br />-Datového souboru<br />-Požadovaných součástí|  
|IsAssembly|Volitelné logická hodnota. Určuje, zda je soubor sestavení.|  
|Viditelné|Volitelné logická hodnota. Označuje, zda zobrazit soubor v **Průzkumníku řešení** v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|CopyToOutputDirectory|Volitelný řetězec. Určuje, zda při kopírování souboru do výstupního adresáře. Hodnoty jsou:<br /><br /> 1.  Nikdy<br />2.  Vždy<br />3.  PreserveNewest|  
  
### <a name="none"></a>Žádné  
 Představuje soubory, které by měl mít žádný atribut role v procesu sestavení.  
  
|Název položky metadat|Popis|  
|---------------|-----------------|  
|DependentUpon|Volitelný řetězec. Určuje soubor, který tento soubor závisí na pro správnou kompilaci.|  
|Generátor|Požadovaný řetězec. Název generátor všech souborů, který se spouští na tuto položku.|  
|LastGenOutput|Požadovaný řetězec. Název souboru, který byl vytvořen generátor všech souborů, který byl spuštěn na tuto položku.|  
|CustomToolNamespace|Požadovaný řetězec. Kód by měl vytvořit obor názvů, ve které žádný soubor generátor, který běží na tuto položku.|  
|Odkaz|Volitelný řetězec. Konvenční cesta, který se má zobrazit, pokud se soubor nachází fyzicky mimo vliv projektu.|  
|Viditelné|Volitelné logická hodnota. Označuje, zda zobrazit soubor v **Průzkumníku řešení** v [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].|  
|CopyToOutputDirectory|Volitelný řetězec. Určuje, zda při kopírování souboru do výstupního adresáře. Hodnoty jsou:<br /><br /> 1.  Nikdy<br />2.  Vždy<br />3.  PreserveNewest|  
  
### <a name="baseapplicationmanifest"></a>BaseApplicationManifest  
 Představuje základní aplikace manifest pro sestavení a obsahuje [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] informace o zabezpečení nasazení.  
  
### <a name="codeanalysisimport"></a>CodeAnalysisImport  
 Představuje FxCop projektu k importu.  
  
### <a name="import"></a>Importovat  
 Představuje sestavení, jejichž obory názvů musí být importovány pomocí [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] kompilátoru.  
  
## <a name="see-also"></a>Viz také  
 [Obecné vlastnosti projektu nástroje MSBuild](../msbuild/common-msbuild-project-properties.md)
