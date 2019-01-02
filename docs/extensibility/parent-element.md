---
title: Nadřazený Element | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, Parent
- Parent element (VSCT XML schema)
ms.assetid: e4624ac8-1b9a-4940-910a-528a661cefad
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c025957bd0d3cf06bf73e1b35b5faa661386a0a5
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53902434"
---
# <a name="parent-element"></a>Nadřazený element
Nadřazené tlačítko nebo pole se seznamem pole může být pouze skupinu. Nadřazené nabídky nebo skupina může být jiné nabídky nebo skupiny. V [commandplacement – element](../extensibility/commandplacement-element.md), tento element je povinná hodnota. v ostatních instancích je volitelný. Pokud tento prvek je vynechán, nadřazený `Group_Undefined:0` bude implicitní.  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<Parent guid="guidMyCommandSet" id="MyParentGroupOrMenu" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|identifikátor GUID|Povinný parametr. Identifikátor GUID identifikátoru GUID a ID příkazu.|  
|id|Povinný parametr. Identifikátor ID identifikátoru GUID a ID příkazu.|  
  
### <a name="child-elements"></a>Podřízené prvky  
 Žádná  
  
### <a name="parent-elements"></a>Nadřazené prvky  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Commandtable – element](../extensibility/commandtable-element.md)|Definuje všechny prvky, které představují příkazy, které poskytuje VSPackage integrovaného vývojového prostředí (IDE). Například položky nabídky, nabídky, panely nástrojů a pole se seznamem.|  
|[Buttons – element](../extensibility/buttons-element.md)|Skupiny [Button element](../extensibility/button-element.md) elementy.|  
|[Menus – element](../extensibility/menus-element.md)|Definuje všechny nabídky, které implementuje VSPackage.|  
|[Groups – element](../extensibility/groups-element.md)|Obsahuje položky, které definují skupiny příkaz VSPackage.|  
  
## <a name="see-also"></a>Viz také:  
 [Soubory tabulky (.vsct) příkaz pro Visual Studio](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)