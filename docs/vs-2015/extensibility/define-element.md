---
title: Definování elementu | Dokumentace Microsoftu
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
- VSCT XML schema elements, Define
- Define element (VSCT XML schema)
ms.assetid: 5aee74e3-de41-4dc6-9618-93e158af56dd
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 7a573413c20c305f3645b1d2795901f344ffb235
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49229180"
---
# <a name="define-element"></a>Define – element
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Definuje symbol dvojice název a hodnotu. Tento symbol lze vyhodnotit podmíněné atributy. Další informace najdete v tématu [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md). Viz také [symboly Element](../extensibility/symbols-element.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
<Define name="Mode" value="Standard" />  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
  
|Atribut|Popis|  
|---------------|-----------------|  
|name|Požadováno. Název symbolu:<br /><br /> název = "Režim"|  
|value|Požadováno. Hodnota symbolu:<br /><br /> Hodnota = "Standard"|  
|Podmínka|Volitelné. Další informace najdete v tématu [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md).|  
  
### <a name="child-elements"></a>Podřízené elementy  
 Žádné  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[CommandTable – element](../extensibility/commandtable-element.md)|Definuje všechny prvky, které představují příkazy, které poskytuje VSPackage integrovaného vývojového prostředí (IDE). Například položky nabídky, nabídky, panely nástrojů a pole se seznamem.|  
  
## <a name="example"></a>Příklad  
  
```  
<Define name="DEMO_UI"/>  
<Define name="MODE" value="Standard"/>  
```  
  
## <a name="see-also"></a>Viz také  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

