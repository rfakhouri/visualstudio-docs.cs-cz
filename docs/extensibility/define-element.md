---
title: "Definování elementu | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- VSCT XML schema elements, Define
- Define element (VSCT XML schema)
ms.assetid: 5aee74e3-de41-4dc6-9618-93e158af56dd
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 35d33f0c440bce6d83c8a4712f0059d7f51a0ff0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="define-element"></a>Definování elementu
Určuje dvojice název a hodnotu symbol. Podmíněné atributy mohou být vyhodnocena tento symbol. Další informace najdete v tématu [podmíněné atributy](../extensibility/vsct-xml-schema-conditional-attributes.md). Viz také [symboly Element](../extensibility/symbols-element.md).  
  
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
|[CommandTable – element](../extensibility/commandtable-element.md)|Definuje všechny elementy, které představují příkazy, které poskytuje VSPackage integrované vývojové prostředí (IDE). Například položky nabídky, nabídek, panely nástrojů a pole se seznamem.|  
  
## <a name="example"></a>Příklad  
  
```  
<Define name="DEMO_UI"/>  
<Define name="MODE" value="Standard"/>  
```  
  
## <a name="see-also"></a>Viz také  
 [Soubory tabulek příkazů sady Visual Studio (.Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)