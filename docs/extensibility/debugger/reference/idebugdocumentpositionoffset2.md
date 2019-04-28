---
title: IDebugDocumentPositionOffset2 | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
helpviewer_keywords:
- IDebugDocumentPositionOffset2 interface
ms.assetid: f1b05db3-50d8-453f-a72f-e68b239236a4
caps.latest.revision: 8
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: cf713ea542901cbde588600d40f144f0fae843e2
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62875255"
---
# <a name="idebugdocumentpositionoffset2"></a>IDebugDocumentPositionOffset2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

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
|[GetRange](../../../extensibility/debugger/reference/idebugdocumentpositionoffset2-getrange.md)|Načte rozsah pro aktuální pozice v dokumentu.|  
  
## <a name="remarks"></a>Poznámky  
 Vrátí stejné informace jako [getrange –](../../../extensibility/debugger/reference/idebugdocumentposition2-getrange.md) ale `char` posun od začátku dokumentu. To představuje dokument jako jeho by existovat na disku, to znamená, jednorozměrné pole znaků, namísto řádku a sloupci informace, které se obvykle vrátí.  
  
## <a name="requirements"></a>Požadavky  
 Záhlaví: Msdbg.h  
  
 Obor názvů: Microsoft.VisualStudio.Debugger.Interop  
  
 Sestavení: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Viz také  
 [IDebugDocumentPosition2](../../../extensibility/debugger/reference/idebugdocumentposition2.md)
