---
title: IEnumJsStackFrames Interface | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 49e7b425-df17-4d7f-87ff-0bc82715c911
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2e8302737fb4abf96c55d3ae70424cc03579b270
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62963322"
---
# <a name="ienumjsstackframes-interface"></a>IEnumJsStackFrames – rozhraní
Implementovaný ladicí program k poskytování zásobníku unwind pro modul jscript9diag.dll pro JavaScript.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
IEnumJsStackFrames : public IUnknown;  
```  
  
## <a name="members"></a>Členové  
  
### <a name="public-methods"></a>Veřejné metody  
  
|Název|Popis|  
|----------|-----------------|  
|[IEnumJsStackFrames::Next – metoda](../../winscript/reference/ienumjsstackframes-next-method.md)|Získá určený počet snímků.|  
|[IEnumJsStackFrames::Reset – metoda](../../winscript/reference/ienumjsstackframes-reset-method.md)|Obnoví rámec zásobníku do polohy před první prvek.|  
  
## <a name="requirements"></a>Požadavky  
 **Záhlaví:** jscript9diag.h  
  
## <a name="see-also"></a>Viz také  
 [Referenční dokumentace skriptovacích rozhraní systému Windows](../../winscript/reference/windows-script-interfaces-reference.md)