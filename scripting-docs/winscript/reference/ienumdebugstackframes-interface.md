---
title: Ienumdebugstackframes – rozhraní | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IEnumDebugStackFrames interface
ms.assetid: 13484429-0140-4f4f-8502-3ca2a0553ed4
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 224c26bccc5443cb20e2ca514ac6df1a111df05e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62963361"
---
# <a name="ienumdebugstackframes-interface"></a>IEnumDebugStackFrames – rozhraní
Vytváří výčet rámců zásobníku odpovídající vlákno.  
  
## <a name="methods"></a>Metody  
 Kromě metod zděděných z `IUnknown`, `IEnumDebugStackFrames` rozhraní poskytuje následující metody.  
  
|Metoda|Popis|  
|------------|-----------------|  
|[IEnumDebugStackFrames::Next](../../winscript/reference/ienumdebugstackframes-next.md)|Načte zadaný počet segmentů v pořadí výčtu.|  
|[IEnumDebugStackFrames::Skip](../../winscript/reference/ienumdebugstackframes-skip.md)|Vynechá zadaný počet segmentů v sekvenci výčtu.|  
|[IEnumDebugStackFrames::Reset](../../winscript/reference/ienumdebugstackframes-reset.md)|Návrat na začátek sekvence výčtu.|  
|[IEnumDebugStackFrames::Clone](../../winscript/reference/ienumdebugstackframes-clone.md)|Vytvoří čítač, který obsahuje stejného stavu jako aktuální enumerátor.|