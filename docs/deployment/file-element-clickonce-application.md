---
title: '&lt;soubor&gt; – Element (aplikace ClickOnce) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-deployment
ms.topic: reference
f1_keywords:
- http://www.w3.org/2000/09/xmldsig#Transform
- urn:schemas-microsoft-com:asm.v2#file
- http://www.w3.org/2000/09/xmldsig#DigestValue
- http://www.w3.org/2000/09/xmldsig#DigestMethod
- http://www.w3.org/2000/09/xmldsig#Transforms
- urn:schemas-microsoft-com:asm.v2#hash
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <file> element [ClickOnce application manifest]
- manifests [ClickOnce], file element
ms.assetid: 56e3490c-eed5-4841-b1bf-eefe778b6ac9
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f1e744071219426c751576f8ca781ad27dfedb61
ms.sourcegitcommit: 1b9c1e333c2f096d35cfc77e846116f8e5054557
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 06/06/2018
ms.locfileid: "34815845"
---
# <a name="ltfilegt-element-clickonce-application"></a>&lt;soubor&gt; – Element (ClickOnce aplikace)
Identifikuje všechny nesestavené soubory stáhli a používá je aplikace.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<file  
    name  
    size  
    group  
    optional  
    writeableType  
>  
    <typelib  
        tlbid  
        version  
        helpdir  
        resourceid  
        flags  
    />  
    <comClass  
        clsid  
        description  
        threadingModel  
        tlbid  
        progid  
        miscStatus  
        miscStatusIcon  
        miscStatusContent  
        miscStatusDocPrint  
        miscStatusThumbnail  
    />  
    <comInterfaceExternalProxyStub  
        iid  
        baseInterface  
        numMethods  
        name  
        tlbid  
        proxyStubClass32  
    />  
    <comInterfaceProxyStub  
        iid  
        baseInterface  
        numMethods  
        name  
        tlbid  
        proxyStubClass32  
    />  
    <windowClass  
        versioned  
    />  
</file>  
```  
  
## <a name="elements-and-attributes"></a>Elementy a atributy  
 `file` Prvek je volitelný. Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`name`|Požadováno. Určuje název souboru.|  
|`size`|Požadováno. Určuje velikost v bajtech souboru.|  
|`group`|Volitelné, pokud `optional` atribut není zadaný, nebo nastavte `false`; požadováno pokud `optional` je `true`. Název skupiny, do které tento soubor patří. Název může být libovolná hodnota řetězce Unicode zvolený vývojářem a slouží pro stahování souborů na vyžádání pomocí <xref:System.Deployment.Application.ApplicationDeployment> třídy.|  
|`optional`|Volitelné. Určuje, zda tento soubor musí spustit stahování, když je aplikace první, nebo zda soubor by měl být umístěn pouze na serveru dokud aplikace požaduje na vyžádání. Pokud `false` nebo undefined, soubor se stáhne, při prvním spuštění nebo instalaci aplikace. Pokud `true`, `group` pro manifest aplikace platná musí být zadána. `optional` nemůže být true, pokud `writeableType` je zadán s hodnotou `applicationData`.|  
|`writeableType`|Volitelné. Určuje, zda je tento soubor datový soubor. Aktuálně je jedinou platnou hodnotou `applicationData`.|  
  
## <a name="typelib"></a>knihovny typů  
 `typelib` Element je volitelným podřízeným prvku souboru. Element popisuje knihovny typů, který patří do komponenty modelu COM. Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`tlbid`|Požadováno. Identifikátor GUID přiřazený knihovny typů.|  
|`version`|Požadováno. Číslo verze knihovny typů.|  
|`helpdir`|Požadováno. Adresář, který obsahuje soubory nápovědy pro komponentu. Může být nulová délka.|  
|`resourceid`|Volitelné. Reprezentace šestnáctkového řetězce identifikátor národního prostředí (LCID). Je jedna do čtyř šestnáctkových číslic bez předpony 0 x a bez úvodní nuly. Identifikátor LCID může mít identifikátor neutrální dílčího jazyka.|  
|`flags`|Volitelné. Řetězcová reprezentace příznaků knihovny typů pro tuto knihovnu typů. Konkrétně je třeba použít jeden z "S omezeným PŘÍSTUPEM", "Řízení", "HIDDEN" a "HASDISKIMAGE".|  
  
## <a name="comclass"></a>comClass  
 `comClass` Element je volitelným podřízeným `file` elementu, ale je nutný, pokud [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace obsahuje komponenty modelu COM má v úmyslu nasadit pomocí bez registrace modelu COM. Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`clsid`|Požadováno. ID třídy komponenty modelu COM, vyjádřený jako identifikátor GUID.|  
|`description`|Volitelné. Název třídy.|  
|`threadingModel`|Volitelné. Model vláken používaný třídami COM v procesu. Pokud tato vlastnost má hodnotu null, použije se žádný model vláken. Součást je vytvořen na hlavní vlákno klienta a volání z jiné vláken přeuspořádány na tento přístup z více vláken. V následujícím seznamu jsou platné hodnoty:<br /><br /> `Apartment`, `Free`, `Both`, a `Neutral`.|  
|`tlbid`|Volitelné. Identifikátor GUID pro knihovnu typů pro tuto součást COM.|  
|`progid`|Volitelné. Závislý na verzi programový identifikátor přidružený komponenty modelu COM. Formát `ProgID` je `<vendor>.<component>.<version>`.|  
|`miscStatus`|Volitelné. Duplicitní položky v sestavení manifest informace poskytované `MiscStatus` klíč registru. Pokud hodnoty `miscStatusIcon`, `miscStatusContent`, `miscStatusDocprint`, nebo `miscStatusThumbnail` nejsou nalezeny atributy, odpovídající výchozí hodnota uvedená v `miscStatus` se používá pro chybějící atributy. Hodnota může být čárkami oddělený seznam hodnot atributů v následující tabulce. Pokud třídy COM je OCX třída, která vyžaduje, můžete použít tento atribut `MiscStatus` hodnoty klíčů registru.|  
|`miscStatusIcon`|Volitelné. Informace poskytované DVASPECT_ICON manifestu duplikuje v sestavení. Může poskytnout ikonu objektu. Hodnota může být čárkami oddělený seznam hodnot atributů v následující tabulce. Pokud třídy COM je OCX třída, která vyžaduje, můžete použít tento atribut `Miscstatus` hodnoty klíčů registru.|  
|`miscStatusContent`|Volitelné. Duplicitní položky v sestavení manifest informací uvedených DVASPECT_CONTENT. Na obrazovce nebo tiskárny můžete získat zobrazitelné složeného dokumentu. Hodnota může být čárkami oddělený seznam hodnot atributů v následující tabulce. Pokud třídy COM je OCX třída, která vyžaduje, můžete použít tento atribut `MiscStatus` hodnoty klíčů registru.|  
|`miscStatusDocPrint`|Volitelné. Duplicitní položky v sestavení manifest informací uvedených DVASPECT_DOCPRINT. Na obrazovce může poskytnout reprezentaci objektu zobrazitelnou jakoby tisku na tiskárně. Hodnota může být čárkami oddělený seznam hodnot atributů v následující tabulce. Pokud třídy COM je OCX třída, která vyžaduje, můžete použít tento atribut `MiscStatus` hodnoty klíčů registru.|  
|`miscStatusThumbnail`|Volitelné. V sestavení manifestu duplikuje informací uvedených DVASPECT_THUMBNAIL. Můžete získat na miniaturu zobrazitelné v procházení nástroji objektu. Hodnota může být čárkami oddělený seznam hodnot atributů v následující tabulce. Pokud třídy COM je OCX třída, která vyžaduje, můžete použít tento atribut `MiscStatus` hodnoty klíčů registru.|  
  
## <a name="cominterfaceexternalproxystub"></a>comInterfaceExternalProxyStub  
 `comInterfaceExternalProxyStub` Element je volitelným podřízeným `file` elementu, ale může být vyžadováno, pokud [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace obsahuje komponenty modelu COM má v úmyslu nasadit pomocí bez registrace modelu COM. Element obsahuje následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`iid`|Požadováno. Rozhraní ID (IID), který poskytuje tento proxy server. Identifikátory IID musí mít okolní složené závorky.|  
|`baseInterface`|Volitelné. Identifikátory IID rozhraní, ze kterého rozhraní odkazuje `iid` je odvozený.|  
|`numMethods`|Volitelné. Počet metody implementované rozhraní.|  
|`name`|Volitelné. Název rozhraní tak, jak se zobrazí v kódu.|  
|`tlbid`|Volitelné. Knihovny typů, který obsahuje popis rozhraní zadané `iid` atribut.|  
|`proxyStubClass32`|Volitelné. Mapuje IID na CLSID v 32bitových proxy knihovny DLL.|  
  
## <a name="cominterfaceproxystub"></a>comInterfaceProxyStub  
 `comInterfaceProxyStub` Element je volitelným podřízeným `file` elementu, ale může být vyžadováno, pokud [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace obsahuje komponenty modelu COM má v úmyslu nasadit pomocí bez registrace modelu COM. Element obsahuje následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`iid`|Požadováno. Rozhraní ID (IID), který poskytuje tento proxy server. Identifikátory IID musí mít okolní složené závorky.|  
|`baseInterface`|Volitelné. Identifikátory IID rozhraní, ze kterého rozhraní odkazuje `iid` je odvozený.|  
|`numMethods`|Volitelné. Počet metody implementované rozhraní.|  
|`Name`|Volitelné. Název rozhraní tak, jak se zobrazí v kódu.|  
|`Tlbid`|Volitelné. Knihovny typů, který obsahuje popis rozhraní zadané `iid` atribut.|  
|`proxyStubClass32`|Volitelné. Mapuje IID na CLSID v 32bitových proxy knihovny DLL.|  
|`threadingModel`|Volitelné. Volitelné. Model vláken používaný třídami COM v procesu. Pokud tato vlastnost má hodnotu null, použije se žádný model vláken. Součást je vytvořen na hlavní vlákno klienta a volání z jiné vláken přeuspořádány na tento přístup z více vláken. V následujícím seznamu jsou platné hodnoty:<br /><br /> `Apartment`, `Free`, `Both`, a `Neutral`.|  
  
## <a name="windowclass"></a>windowClass  
 `windowClass` Element je volitelným podřízeným `file` elementu, ale může být vyžadováno, pokud [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] aplikace obsahuje komponenty modelu COM má v úmyslu nasadit pomocí bez registrace modelu COM. Element odkazuje na třídu okno definované komponenty modelu COM, kterou musí mít verzi na něho použít. Element obsahuje následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`versioned`|Volitelné. Určuje, zda okno interní třídy název používaný v registraci obsahuje verzi nástroje sestavení, které obsahuje třídu oken. Hodnota tohoto atributu může být `yes` nebo `no`. Výchozí hodnota je `yes`. Hodnota `no` musí být použit pouze pokud je definována stejnou třídu oken souběžně sdílená komponenta a komponentu ekvivalentní jiný--souběžného a chcete je považovat za stejnou třídu oken. Všimněte si, že platí obvyklé pravidla o registrace tříd oken – pouze první součást, která registruje třídu oken budete moct zaregistrovat, protože nemá na verzi, použije na ni.|  
  
## <a name="hash"></a>hash  
 `hash` Element je volitelným podřízeným `file` elementu. `hash` Element nemá žádné atributy.  
  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] používá algoritmické hodnotu hash všech souborů v aplikaci jako kontrolu zabezpečení, ujistěte se, že žádné soubory byly změněny po nasazení. Pokud `hash` element neuvedete, nebude provedena kontrola. Proto vynechání `hash` element se nedoporučuje.  
  
 Pokud manifestu obsahuje soubor, který není s použitím algoritmu hash, že manifest nemůže být digitálně podepsané, protože uživatelé nemůže ověřit obsah souboru bez otisku.  
  
## <a name="dsigtransforms"></a>dsig:TRANSFORMS  
 `dsig:Transforms` Je požadovaný podřízený element `hash` elementu. `dsig:Transforms` Element nemá žádné atributy.  
  
## <a name="dsigtransform"></a>dsig:Transform  
 `dsig:Transform` Je požadovaný podřízený element `dsig:Transforms` elementu. `dsig:Transform` Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Algorithm`|Algoritmus použitý k vypočítat hodnotu hash pro tento soubor. Aktuálně pouze hodnota používaná metodou [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] je `urn:schemas-microsoft-com:HashTransforms.Identity`.|  
  
## <a name="dsigdigestmethod"></a>dsig: DigestMethod  
 `dsig:DigestMethod` Je požadovaný podřízený element `hash` elementu. `dsig:DigestMethod` Element má následující atributy.  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`Algorithm`|Algoritmus použitý k vypočítat hodnotu hash pro tento soubor. Aktuálně pouze hodnota používaná metodou [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] je `http://www.w3.org/2000/09/xmldsig#sha1`.|  
  
## <a name="dsigdigestvalue"></a>dsig: DigestValue  
 `dsig:DigestValue` Je požadovaný podřízený element `hash` elementu. `dsig:DigestValue` Element nemá žádné atributy. Jeho textová hodnota je vypočtená hodnota hash pro zadaný soubor.  
  
## <a name="remarks"></a>Poznámky  
 Tento element identifikuje všechny nesestavené soubory, které tvoří aplikaci a na konkrétní hodnoty hash pro ověření souboru. Tento element může obsahovat také data izolace modelu COM (Component Object) přidružené k souboru. Pokud se změní soubor, soubor manifestu aplikace také musí aktualizovat, aby odrážely změny.  
  
## <a name="example"></a>Příklad  
 Následující příklad kódu ukazuje `file` prvky v aplikaci manifest aplikace nasazené pomocí [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].  
  
```xml  
<file name="Icon.ico" size="9216">  
  <hash>  
    <dsig:Transforms>  
      <dsig:Transform Algorithm="urn:schemas-microsoft-com:HashTransforms.Identity" />  
    </dsig:Transforms>  
    <dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1" />  
    <dsig:DigestValue>lVoj+Rh6RQ/HPNLOdayQah5McrI=</dsig:DigestValue>  
  </hash>  
</file>  
```  
  
## <a name="see-also"></a>Viz také  
 [ClickOnce – manifest aplikace ](../deployment/clickonce-application-manifest.md)