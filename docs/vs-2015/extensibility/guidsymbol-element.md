---
title: Guidsymbol – Element | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- VSCT XML schema elements, GuidSymbol
- GuidSymbol element (VSCT XML schema)
ms.assetid: 11fb3545-8974-4776-9a54-6b6e7739ae31
caps.latest.revision: 9
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 5f11ed48d9dcf961228957cf15db3815c00d14d7
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54770068"
---
# <a name="guidsymbol-element"></a>GuidSymbol – element
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

`GuidSymbol` Prvek obsahuje GUID GUID:ID pár, který představuje nabídky, skupiny nebo příkaz. ID pochází z `IDSymbol` prvek `GuidSymbol` elementu. `GuidSymbol` Element má `name` atribut, který poskytuje popisný název pro identifikátor GUID, který je součástí `value` atribut.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<GuidSymbol name="guidMyCommandSet" value="{xxxxxxxxxxxxx-xxxx-xxxx-xxxxxxxxxxxx}">  
  <IDSymbol>... </IDSymbol>  
  <IDSymbol>... </IDSymbol>  
</GuidSymbol>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|name|Povinný parametr. Název symbolu identifikátor GUID.|  
|value|Povinný parametr. Identifikátor GUID symbol identifikátor GUID.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[IDSymbol – element](../extensibility/idsymbol-element.md)|Obsahuje ID GUID:ID pár, který představuje nabídky, skupiny nebo příkaz.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Symbols – element](../extensibility/symbols-element.md)|Skupiny `GuidSymbol` elementy v souboru .vsct.|  
  
## <a name="remarks"></a>Poznámky  
 Obvykle souboru .vsct obsahuje tři `GuidSymbol` prvků v jeho `Symbols` části, jeden pro samotném balíčku, z nich je pro příkaz set (kolekce nabídek, skupiny a příkazy, které zpřístupní balíček) a jeden pro rastrové obrázky, zadejte ikony pro tlačítka a další vizuální komponenty. Každý `IDSymbol` element v danou `GuidSymbol` element musí mít jedinečný `value`. Ale `IDSymbol` prvky, které mají stejné hodnoty může existovat v balíčku tak dlouho, dokud mají jiné nadřazené položky.  
  
## <a name="see-also"></a>Viz také  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
