---
title: IDebugDocumentPositionOffset2 | Dokumentace Microsoftu
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
- IDebugDocumentPositionOffset2 interface
ms.assetid: f1b05db3-50d8-453f-a72f-e68b239236a4
caps.latest.revision: 8
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: d10c71340b6ad6c7e76753b40c3bef55d8e7e606
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42665981"
---
# <a name="idebugdocumentpositionoffset2"></a>IDebugDocumentPositionOffset2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [IDebugDocumentPositionOffset2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugdocumentpositionoffset2).  
  
Představuje pozici ve zdrojovém souboru jako odsazení znaku.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugDocumentPositionOffset2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Implementované integrovaným vývojovým prostředím a spotřebovávány ladicí stroj.  
  
## <a name="methods"></a>Metody  
 V následující tabulce jsou uvedeny metody objektu `IDebugDocumentPositionOffset2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Getrange –](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2-getrange.md)|Načte rozsah pro aktuální pozice v dokumentu.|  
  
## <a name="remarks"></a>Poznámky  
 Vrátí stejné informace jako [getrange –](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md) ale `char` posun od začátku dokumentu. To představuje dokument jako jeho by existovat na disku, to znamená, jednorozměrné pole znaků, namísto řádku a sloupci informace, které se obvykle vrátí.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)

