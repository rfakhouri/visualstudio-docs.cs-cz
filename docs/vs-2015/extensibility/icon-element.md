---
title: Icon – Element | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- VSCT XML schema elements, Icon
- Icon element (VSCT XML schema)
ms.assetid: 73c58fe3-d53c-4f4e-b025-29567c6cbb7c
caps.latest.revision: 6
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 31a6e0cf18422118c184f290fc8200d9c9263356
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49186670"
---
# <a name="icon-element"></a>Icon – element
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Atribut guid ikonu značky je identifikátor guid definované rastrový obrázek.  Atribut id vybere slotu v pruhu rastrového obrázku. Tento element je volitelný.  Pokud tento prvek je vynechán hodnotu **guidOfficeIcon:msotcidNoIcon** bude implicitní.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Icon guid="guidImages" id="bmpPic1" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|identifikátor GUID|Požadováno. Identifikátor guid definované rastrový obrázek.|  
|id|Požadováno. Vybere slotu v pruhu rastrového obrázku.|  
  
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

