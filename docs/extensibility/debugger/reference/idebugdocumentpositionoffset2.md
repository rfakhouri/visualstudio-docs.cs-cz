---
title: IDebugDocumentPositionOffset2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDebugDocumentPositionOffset2 interface
ms.assetid: f1b05db3-50d8-453f-a72f-e68b239236a4
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 12b3d9781348beb69bb2f4923dd5d5b311f157c0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idebugdocumentpositionoffset2"></a>IDebugDocumentPositionOffset2
Představuje pozici ve zdrojovém souboru jako odsazení znaku.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
IDebugDocumentPositionOffset2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Poznámky pro implementátory  
 Implementovat rozhraní IDE a spotřebovávají ladění moduly.  
  
## <a name="methods"></a>Metody  
 Následující tabulka uvádí metody `IDebugDocumentPositionOffset2`.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[Getrange –](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2-getrange.md)|Načte rozsah pro aktuální pozici dokumentu.|  
  
## <a name="remarks"></a>Poznámky  
 Tento příkaz vrátí stejné informace jako [getrange –](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md) ale v `char` posun od začátku dokumentu. To představuje dokumentu jako ho by existovat na disku, který je jednorozměrné pole znaků, místo řádku a ve sloupci informace, které se vrátí normálně.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)