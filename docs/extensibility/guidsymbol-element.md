---
title: GuidSymbol Element | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSCT XML schema elements, GuidSymbol
- GuidSymbol element (VSCT XML schema)
ms.assetid: 11fb3545-8974-4776-9a54-6b6e7739ae31
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: d5089d87156bd5eb191176fe73ab19a01d497b90
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="guidsymbol-element"></a>GuidSymbol Element
`GuidSymbol` Element obsahuje identifikátor GUID, které odpovídá páru GUID:ID představující nabídky, skupinu nebo příkaz. ID pochází z `IDSymbol` element v `GuidSymbol` elementu. `GuidSymbol` Element má `name` atribut, který poskytuje popisný název pro identifikátor GUID, který je součástí `value` atribut.  
  
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
|name|Požadováno. Název symbolu identifikátor GUID.|  
|value|Požadováno. Identifikátor GUID GUID symbolu.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[IDSymbol – element](../extensibility/idsymbol-element.md)|Obsahuje ID, které odpovídá páru GUID:ID představující nabídky, skupinu nebo příkaz.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Symbols – element](../extensibility/symbols-element.md)|Skupiny `GuidSymbol` elementů v souboru .vsct.|  
  
## <a name="remarks"></a>Poznámky  
 Obvykle soubor .vsct obsahuje tři `GuidSymbol` elementů v jeho `Symbols` části, jeden pro balíček sám sebe, jednu pro sadu příkazů (shromažďování nabídek, skupiny a příkazy, které zpřístupní balíčku) a jeden pro rastrové obrázky, které poskytují ikony pro tlačítek a jiných vizuální součásti. Každý `IDSymbol` element v danou `GuidSymbol` element musí mít jedinečnou `value`. Ale `IDSymbol` prvky, které mají stejné hodnoty může existovat v balíčku, dokud mají jiné nadřazené položky.  
  
## <a name="see-also"></a>Viz také  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)