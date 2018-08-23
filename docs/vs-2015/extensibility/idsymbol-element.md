---
title: Idsymbol – Element | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IDSymbol element (VSCT XML schema)
- VSCT XML schema elements, IDSymbol
ms.assetid: 760cfd20-3c06-422c-9103-98bfa1f387f8
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f3ab239c85fbf3e9ebc83825750b78a1e6fdbf7f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627678"
---
# <a name="idsymbol-element"></a>IDSymbol – element
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idsymbol – Element](https://docs.microsoft.com/visualstudio/extensibility/idsymbol-element).  
  
`IDSymbol` Prvek obsahuje ID GUID:ID pár, který představuje nabídky, skupiny nebo příkaz. Identifikátor GUID pochází z nadřazeného `GuidSymbol` elementu. `IDSymbol` Element má `name` atribut, který poskytuje popisný název pro Identifikátor, který je součástí `value` atribut.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<IDSymbol name=ElementName value="0x0010" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|name|Požadováno. Název symbolu ID.|  
|value|Požadováno. Číselná hodnota ID ID symbolu.|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[GuidSymbol – element](../extensibility/guidsymbol-element.md)|Obsahuje GUID GUID:ID pár, který představuje nabídky, skupiny nebo příkaz. Skupiny `IDSymbol` elementy.|  
  
## <a name="remarks"></a>Poznámky  
 Každý `IDSymbol` element v danou `GuidSymbol` element musí mít jedinečný `value`. Ale `IDSymbol` prvky, které mají stejné hodnoty může existovat v balíčku tak dlouho, dokud mají jiné nadřazené položky.  
  
## <a name="see-also"></a>Viz také  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

