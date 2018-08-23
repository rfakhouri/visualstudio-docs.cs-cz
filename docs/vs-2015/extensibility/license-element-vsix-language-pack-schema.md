---
title: Licence Element (VSIX Language Pack Schema) | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57dac3b7-0cdd-405c-9af5-30ed9ca45e53
caps.latest.revision: 9
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ecf1913878137d84346275beccb512027f74f8f3
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42668856"
---
# <a name="license-element-vsix-language-pack-schema"></a>Licence – Element (VSIX Language Pack schéma)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [licence – Element (VSIX Language Pack schéma)](https://docs.microsoft.com/visualstudio/extensibility/license-element-vsix-language-pack-schema).  
  
Volitelné. Cesta lokalizovanou verzi souboru s licencí pro rozšíření.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<License>FilePath\license.txt</License>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|Žádné||  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Žádné||  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[VSIX LanguagePack Element](../extensibility/vsixlanguagepack-element-vsix-language-pack-schema.md)|Požadováno. Obsahuje kořenový prvek pro jazykové sady VSIX.|  
  
## <a name="text-value"></a>Textová hodnota  
 Relativní cesta lokalizované licenční soubor, který se má zobrazit.  
  
## <a name="remarks"></a>Poznámky  
 Pokud `License` element definován, pak během instalace se zobrazí text určené licenční soubor a uživatel musí přijmout licenci, abyste mohli pokračovat.  
  
## <a name="element-information"></a>Informace o elementu  
  
|||  
|-|-|  
|Obor názvů|http://schemas.microsoft.com/developer/vsx-schema-lp/2010|  
|Název schématu|VSIX Language Pack Schema|  
|Soubor ověření|VSIXLanguagePackSchema.xsd|  
|Může být prázdné.|Nelze použít|  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu VSX Language Pack](../extensibility/vsx-language-pack-schema-reference.md)   
 [Lokalizace balíčků VSIX](../extensibility/localizing-vsix-packages.md)   
 [Referenční dokumentace schématu 1.0 rozšíření VSIX](http://msdn.microsoft.com/en-us/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)

