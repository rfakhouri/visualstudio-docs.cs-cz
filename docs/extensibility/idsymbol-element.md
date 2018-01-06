---
title: IDSymbol Element | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDSymbol element (VSCT XML schema)
- VSCT XML schema elements, IDSymbol
ms.assetid: 760cfd20-3c06-422c-9103-98bfa1f387f8
caps.latest.revision: "7"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 004b40acb50fe85604d0a3cfa9f5626891fa66a4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idsymbol-element"></a>IDSymbol Element
`IDSymbol` Element obsahuje ID, které odpovídá páru GUID:ID představující nabídky, skupinu nebo příkaz. Identifikátor GUID pochází z nadřazené `GuidSymbol` elementu. `IDSymbol` Element má `name` atribut, který poskytuje popisný název pro dané ID, který je součástí `value` atribut.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<IDSymbol name=ElementName value="0x0010" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|name|Požadováno. Název ID symbolu.|  
|value|Požadováno. Číselná hodnota ID ID symbolu.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[GuidSymbol – element](../extensibility/guidsymbol-element.md)|Obsahuje identifikátor GUID, které odpovídá páru GUID:ID představující nabídky, skupinu nebo příkaz. Skupiny `IDSymbol` elementy.|  
  
## <a name="remarks"></a>Poznámky  
 Každý `IDSymbol` element v danou `GuidSymbol` element musí mít jedinečnou `value`. Ale `IDSymbol` prvky, které mají stejné hodnoty může existovat v balíčku, dokud mají jiné nadřazené položky.  
  
## <a name="see-also"></a>Viz také  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)