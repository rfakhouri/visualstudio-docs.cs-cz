---
title: Idebugdocumenttextevents – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentTextEvents interface
ms.assetid: 341b20fd-994c-4030-a06b-6c66ad38c35d
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bec89ae81d79fb7b0d822cafe2bf44f0ecd8ad81
ms.sourcegitcommit: 8bf9e51c77a5a602fab9513b9187e59e57dfebad
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/16/2019
ms.locfileid: "54345654"
---
# <a name="idebugdocumenttextevents-interface"></a>IDebugDocumentTextEvents – rozhraní
Poskytuje události, které naznačují změny přidružené textový dokument.  
  
> [!NOTE]
>  Při události v tomto rozhraní fire změní textu dokumentu. Obslužné rutiny událostí může načíst nový text pomocí `IDebugDocumentText` rozhraní.  
  
 Kromě metod zděděných z `IUnknown`, `IDebugDocumentTextEvents` rozhraní poskytuje následující metody.  
  
## <a name="methods-in-vtable-order"></a>Metody v tabulce Vtable pořadí  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IDebugDocumentTextEvents::onDestroy](../../winscript/reference/idebugdocumenttextevents-ondestroy.md)|Označuje, že došlo ke zničení zdrojový dokument a již není platný|  
|[IDebugDocumentTextEvents::onInsertText](../../winscript/reference/idebugdocumenttextevents-oninserttext.md)|Označuje, že byl přidán nový text do dokumentu|  
|[IDebugDocumentTextEvents::onRemoveText](../../winscript/reference/idebugdocumenttextevents-onremovetext.md)|Označuje, že text byl odebrán z dokumentu.|  
|[IDebugDocumentTextEvents::onReplaceText](../../winscript/reference/idebugdocumenttextevents-onreplacetext.md)|Označuje, že byl nahrazen text.|  
|[IDebugDocumentTextEvents::onUpdateTextAttributes](../../winscript/reference/idebugdocumenttextevents-onupdatetextattributes.md)|Označuje, že došlo ke změně textu atributy přidružené k základní pozice rozsahu znaků.|  
|[IDebugDocumentTextEvents::onUpdateDocumentAttributes](../../winscript/reference/idebugdocumenttextevents-onupdatedocumentattributes.md)|Označuje, že změnit atributy dokumentu.|