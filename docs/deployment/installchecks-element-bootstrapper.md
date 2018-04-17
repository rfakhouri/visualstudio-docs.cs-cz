---
title: '&lt;InstallChecks&gt; prvek (zavaděče) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-deployment
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- <InstallChecks> element [bootstrapper]
ms.assetid: ad329c87-b0ad-4304-84de-ae9496514c42
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: dfd01eb4aa67af9e23a7c8c348bcacb263ccb6f6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="ltinstallchecksgt-element-bootstrapper"></a>&lt;InstallChecks&gt; – Element (zaváděcího nástroje)
`InstallChecks` Element podporuje spouštění různých testů na místním počítači a ujistěte se, že byly nainstalovány všechny příslušné požadavky pro aplikaci.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<InstallChecks>  
    <AssemblyCheck   
        Property  
        Name  
        PublicKeyToken  
        Version  
        Language  
        ProcessorArchitecture  
    />  
    <RegistryCheck  
        Property  
        Key  
        Value  
    />  
    <ExternalCheck   
        PackageFile  
        Property  
        Arguments  
    />  
    <FileCheck   
        Property  
        FileName  
        SearchPath  
        SpecialFolder  
        SearchDepth  
    />  
    <MsiProductCheck   
        Property  
        Product  
        Feature  
    />  
    <RegistryFileCheck   
        Property  
        Key  
        Value  
        FileName  
        SearchDepth  
    />  
</InstallChecks>  
```  
  
## <a name="assemblycheck"></a>AssemblyCheck  
 Tento element je volitelný podřízený prvek `InstallChecks`. Pro každou instanci `AssemblyCheck`, zavaděč zajistí, že sestavení identifikované prvkem existuje v globální mezipaměti sestavení (GAC). Neobsahuje žádné elementy a má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Property`|Požadováno. Název vlastnosti k ukládání výsledků. Tuto vlastnost lze odkazovat z testu pod `InstallConditions` element, který je podřízená z `Command` elementu. Další informace najdete v tématu [ \<příkazy > Element](../deployment/commands-element-bootstrapper.md).|  
|`Name`|Požadováno. Plně kvalifikovaný název sestavení, které chcete zkontrolovat.|  
|`PublicKeyToken`|Požadováno. Zkrácenou formou veřejný klíč přidružený k tomuto silně pojmenovaných sestavení. Ve všech sestaveních uložené v mezipaměti GAC musí mít název, verzi a veřejný klíč.|  
|`Version`|Požadováno. Verze sestavení.<br /><br /> Číslo verze má formát \< *hlavní verzi*>.\< *podverze*>.\< *verze sestavení*>.\< *verze revize*>.|  
|`Language`|Volitelné. Jazyk lokalizovaného sestavení. Výchozí hodnota je `neutral`.|  
|`ProcessorArchitecture`|Volitelné. Procesor počítače, který je cílem této instalace. Výchozí hodnota je `msil`.|  
  
## <a name="externalcheck"></a>ExternalCheck  
 Tento element je volitelný podřízený prvek `InstallChecks`. Pro každou instanci `ExternalCheck`, zaváděcí nástroj spustit s názvem externí program v samostatném procesu a uloží jeho ukončovací kód ve vlastnosti indikován `Property`. `ExternalCheck` je užitečná pro implementaci složitých závislostí, nebo pokud je jediným způsobem, jak kontrolovat existenci součást vytvoří instanci.  
  
 `ExternalCheck` neobsahuje žádné elementy a má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Property`|Požadováno. Název vlastnosti k ukládání výsledků. Tuto vlastnost lze odkazovat z testu pod `InstallConditions` element, který je podřízená z `Command` elementu. Další informace najdete v tématu [ \<příkazy > Element](../deployment/commands-element-bootstrapper.md).|  
|`PackageFile`|Požadováno. Externí program pro spuštění. Program musí být součástí instalační balíček pro distribuci.|  
|`Arguments`|Volitelné. Poskytuje argumentů příkazového řádku pro spustitelný soubor s názvem podle `PackageFile`.|  
  
## <a name="filecheck"></a>FileCheck  
 Tento element je volitelný podřízený prvek `InstallChecks`. Pro každou instanci `FileCheck`, zaváděcí nástroj určí, zda existuje uvedeného souboru a vrátí číslo verze souboru. Pokud soubor nemá číslo verze, zaváděcí nástroj nastaví vlastnost s názvem v `Property` na hodnotu 0. Pokud soubor neexistuje, `Property` není nastavený na žádnou hodnotu.  
  
 `FileCheck` neobsahuje žádné elementy a má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Property`|Požadováno. Název vlastnosti k ukládání výsledků. Tuto vlastnost lze odkazovat z testu pod `InstallConditions` element, který je podřízená z `Command` elementu. Další informace najdete v tématu [ \<příkazy > Element](../deployment/commands-element-bootstrapper.md).|  
|`FileName`|Požadováno. Název souboru najít.|  
|`SearchPath`|Požadováno. Disk nebo složku, do které chcete vyhledat soubor. Pokud to musí být relativní cesta `SpecialFolder` je přiřazen, jinak, musí být absolutní cesta.|  
|`SpecialFolder`|Volitelné. Složka, která má zvláštní význam systému Windows nebo do [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]. Ve výchozím nastavení se interpretovat `SearchPath` jako absolutní cesta. Platné hodnoty patří:<br /><br /> `AppDataFolder`. Složka dat aplikace pro tuto [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace; specifické pro aktuálního uživatele.<br /><br /> `CommonAppDataFolder`. Složka dat aplikace používané všichni uživatelé.<br /><br /> `CommonFilesFolder`. Složka společné soubory pro aktuálního uživatele.<br /><br /> `LocalDataAppFolder`. Složka dat pro-roaming aplikace.<br /><br /> `ProgramFilesFolder`. Standardní složce Program Files pro 32bitové aplikace.<br /><br /> `StartUpFolder`. Složky, která obsahuje všechny aplikace, které jsou spuštěny při spuštění systému.<br /><br /> `SystemFolder`. Složky, která obsahuje 32bitová verze systémové knihovny DLL.<br /><br /> `WindowsFolder`. Složky, která obsahuje instalaci systému Windows.<br /><br /> `WindowsVolume`. Disk nebo oddíl, který obsahuje instalaci systému Windows.|  
|`SearchDepth`|Volitelné. Hloubka pro prohledání dílčí složky s názvem souboru. Hledání je nejprve v úrovni. Výchozí hodnota je 0, který omezuje vyhledávání na složku nejvyšší úrovně určeného `SpecialFolder` a **SearchPath**.|  
  
## <a name="msiproductcheck"></a>MsiProductCheck  
 Tento element je volitelný podřízený prvek `InstallChecks`. Pro každou instanci `MsiProductCheck`, zaváděcí nástroj zkontroluje, jestli má zadanou instalaci Instalační služby systému Windows spustit, dokud nebude dokončena. Hodnota vlastnosti je nastavena v závislosti na stavu nainstalovaného produktu. Kladné celé číslo označuje, že je nainstalován produkt, 0 nebo -1 označuje není nainstalována. (Podrobnosti viz funkce sady SDK Instalační služby systému Windows MsiQueryFeatureState Další informace.) . Pokud není nainstalována Instalační služba systému Windows v počítači, `Property` není nastaven.  
  
 `MsiProductCheck` neobsahuje žádné elementy a má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Property`|Požadováno. Název vlastnosti k ukládání výsledků. Tuto vlastnost lze odkazovat z testu pod `InstallConditions` element, který je podřízená z `Command` elementu. Další informace najdete v tématu [ \<příkazy > Element](../deployment/commands-element-bootstrapper.md).|  
|`Product`|Požadováno. Identifikátor GUID pro nainstalovaný produkt.|  
|`Feature`|Volitelné. Identifikátor GUID pro konkrétní funkci nainstalované aplikace.|  
  
## <a name="registrycheck"></a>RegistryCheck  
 Tento element je volitelný podřízený prvek `InstallChecks`. Pro každou instanci `RegistryCheck`, zaváděcí nástroj zkontroluje, zda zadaný klíč registru existuje, nebo jestli má uvedenou hodnotu.  
  
 `RegistryCheck` neobsahuje žádné elementy a má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Property`|Požadováno. Název vlastnosti k ukládání výsledků. Tuto vlastnost lze odkazovat z testu pod `InstallConditions` element, který je podřízená z `Command` elementu. Další informace najdete v tématu [ \<příkazy > Element](../deployment/commands-element-bootstrapper.md).|  
|`Key`|Požadováno. Název klíče registru.|  
|`Value`|Volitelné. Název hodnoty registru k načtení. Ve výchozím nastavení se vrátí text výchozí hodnota. `Value` musí být řetězec nebo typu DWORD.|  
  
## <a name="registryfilecheck"></a>RegistryFileCheck  
 Tento element je volitelný podřízený prvek `InstallChecks`. Pro každou instanci `RegistryFileCheck`, zaváděcí nástroj načte verze zadaného souboru, nejprve se pokouší načíst cestu k souboru ze zadaného klíče registru. To je zvlášť užitečné, pokud chcete vyhledat soubor v adresáři, zadaný jako hodnota v registru.  
  
 `RegistryFileCheck` neobsahuje žádné elementy a má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Property`|Požadováno. Název vlastnosti k ukládání výsledků. Tuto vlastnost lze odkazovat z testu pod `InstallConditions` element, který je podřízená z `Command` elementu. Další informace najdete v tématu [ \<příkazy > Element](../deployment/commands-element-bootstrapper.md).|  
|`Key`|Požadováno. Název klíče registru. Jeho hodnota je interpretována jako cesta k souboru, pokud `File` nastavený atribut. Pokud tento klíč neexistuje, `Property` není nastaven.|  
|`Value`|Volitelné. Název hodnoty registru k načtení. Ve výchozím nastavení se vrátí text výchozí hodnota. `Value` musí být řetězec.|  
|`FileName`|Volitelné. Název souboru. -Li zadána, hodnota získaná z klíče registru se předpokládá, že jako cestu k adresáři a tento název je připojen k němu. Pokud není zadaný, předpokládá se, že hodnota vrácená z registru je být úplná cesta k souboru.|  
|`SearchDepth`|Volitelné. Hloubka pro prohledání dílčí složky s názvem souboru. Hledání je nejprve v úrovni. Výchozí hodnota je 0, který omezuje vyhledávání na složku nejvyšší úrovně určená hodnotou klíče registru.|  
  
## <a name="remarks"></a>Poznámky  
 Zatímco prvky pod `InstallChecks` definovat testy ke spuštění, nespouštějí je. Chcete-li spustit testy, je nutné vytvořit `Command` prvky pod `Commands` elementu.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `InstallChecks` element jak se používá v souboru produktu [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)].  
  
```  
<InstallChecks>  
    <ExternalCheck Property="DotNetInstalled" PackageFile="dotnetchk.exe" />  
    <RegistryCheck Property="IEVersion" Key="HKLM\Software\Microsoft\Internet Explorer" Value="Version" />  
</InstallChecks>  
```  
  
## <a name="installconditions"></a>InstallConditions  
 Když `InstallChecks` jsou vyhodnoceny, produkují vlastnosti. Vlastnosti jsou pak používány `InstallConditions` k určení, zda by měl nainstalovat balíček, obejít nebo nezdaří. Následující tabulka uvádí `InstallConditions`:  
  
|||  
|-|-|  
|`FailIf`|Pokud existuje `FailIf` podmínka vyhodnocena jako true, balíček se nezdaří. Zbytek podmínky, nebudou hodnocené.|  
|`BypassIf`|Pokud existuje `BypassIf` podmínka vyhodnocena jako true, balíček bude možné obejít. Zbytek podmínky, nebudou hodnocené.|  
  
## <a name="predefined-properties"></a>Předdefinované vlastnosti  
 Následující tabulka uvádí `BypassIf` a `FailIf` prvky:  
  
|Vlastnost|Poznámky|Možné hodnoty|  
|--------------|-----------|---------------------|  
|`Version9X`|Číslo verze operačního systému Windows 9 X.|4.10 = Windows 98|  
|`VersionNT`|Číslo verze operačního systému Windows NT.|Major.Minor.ServicePack<br /><br /> 5.0 = Windows 2000<br /><br /> 5.1.0 = systém Windows XP<br /><br /> 5.1.2 = Windows XP Professional SP2<br /><br /> 5.2.0 = Windows Server 2003|  
|`VersionNT64`|Číslo verze 64bitová verze systému Windows NT operačního systému.|Stejné jako výše uvedené.|  
|`VersionMsi`|Číslo verze služby Windows Installer.|2.0 = Instalační služba systému Windows 2.0|  
|`AdminUser`|Určuje, zda má uživatel oprávnění správce na operační systém na základě systému Windows NT.|0 = bez oprávnění správce<br /><br /> 1 = oprávnění správce|  
  
 Například služba neblokuje instalaci na počítač se systémem Windows 95, použijte například následující kód:  
  
```  
<!-- Block install on Windows 95 -->  
    <FailIf Property="Version9X" Compare="VersionLessThan" Value="4.10" String="InvalidPlatform"/>  
```  
  
## <a name="see-also"></a>Viz také  
 [\<Příkazy > elementu](../deployment/commands-element-bootstrapper.md)   
 [Referenční schéma balíčku a produktu](../deployment/product-and-package-schema-reference.md)