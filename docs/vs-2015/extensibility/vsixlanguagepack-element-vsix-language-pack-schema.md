---
title: Element VSIXLanguagePack (VSIX Language Pack Schema) | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
ms.assetid: 767f5c22-8b87-49ca-92aa-a7a3f026469f
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 7b4ba4e98b8b2d42485a7594d5bab658e1bd6ccb
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54786097"
---
# <a name="vsixlanguagepack-element-vsix-language-pack-schema"></a>Element VSIXLanguagePack (VSIX Language Pack Schema)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Povinný parametr. Obsahuje kořenový prvek pro jazykové sady VSIX. Jazykové sady VSIX obsahuje informace lokalizovaného instalačního balíčku VSIX.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<VSIXLanguagePack>  
  <LocalizedName>...</LocalizedName>  
  <LocalizedDescription>...</LocalizedDescription>  
  <MoreInfoURL>...</MoreInfoURL>  
  <License>...</License>  
</VSIXLanguagePack>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|`xmlns`|XML obor názvů, ve kterém je definována schématu jazykové sady VSIX.|  
  
## <a name="xmlns-attribute"></a>Atribut xmlns.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`http://schemas.microsoft.com/developer/vsx-schema-lp/2010`|Povinný parametr. Umístění souboru, který definuje schéma pro jazykové sady.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[LocalizedName – element](../extensibility/localizedname-element-vsix-language-pack-schema.md)|Povinný parametr. Lokalizovaný název rozšíření k instalaci.|  
|[LocalizedDescription – element](../extensibility/localizeddescription-element-vsix-language-pack-schema.md)|Povinný parametr. Lokalizovaný popis rozšíření k instalaci.|  
|[MoreInfoURL – element](../extensibility/moreinfourl-element-vsix-language-pack-schema.md)|Volitelné. Odkaz na lokalizované informace o rozšíření.|  
|[License – element](../extensibility/license-element-vsix-language-pack-schema.md)|Volitelné. Cesta lokalizovanou verzi souboru s licencí pro rozšíření.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Žádná||  
  
## <a name="element-information"></a>Informace o elementu  
  
|                 |                                                           |
|-----------------|-----------------------------------------------------------|
|    Obor názvů    | http://schemas.microsoft.com/developer/vsx-schema-lp/2010 |
|   Název schématu   |                 VSIX Language Pack Schema                 |
| Soubor ověření |                VSIXLanguagePackSchema.xsd                 |
|  Může být prázdné.   |                            Ne                             |
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace schématu VSX Language Pack](../extensibility/vsx-language-pack-schema-reference.md)   
 [Lokalizace balíčků VSIX](../extensibility/localizing-vsix-packages.md)   
 [Referenční dokumentace schématu 1.0 rozšíření VSIX](http://msdn.microsoft.com/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)
