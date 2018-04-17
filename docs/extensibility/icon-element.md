---
title: Element ikony | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, Icon
- Icon element (VSCT XML schema)
ms.assetid: 73c58fe3-d53c-4f4e-b025-29567c6cbb7c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: f15dcfec5c89c6bf2b2ae68ea29e18890dc9187e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="icon-element"></a>Icon – Element
Atribut guid ikonu značky je identifikátor guid definované rastrového obrázku.  Atribut id vybere přihrádky v pruhu rastrového obrázku. Tento element je volitelný.  Pokud je vynechán tento element hodnotu **guidOfficeIcon:msotcidNoIcon** bude implicitní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Icon guid="guidImages" id="bmpPic1" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|Identifikátor GUID|Požadováno. Identifikátor guid definované rastrového obrázku.|  
|id|Požadováno. Vybere přihrádky v pruhu rastrového obrázku.|  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|Žádné|Žádné|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[Buttons – element](../extensibility/buttons-element.md)||  
  
## <a name="see-also"></a>Viz také  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)