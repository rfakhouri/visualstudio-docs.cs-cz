---
title: Idiaenumsegments::Skip – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaEnumSegments::Skip method
ms.assetid: ec67039f-da8c-4e70-8db7-957d7d5281e8
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3e8fb7de90f43b6f8c4992366993c0c3d8409aba
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53917576"
---
# <a name="idiaenumsegmentsskip"></a>IDiaEnumSegments::Skip
Vynechá zadaný počet segmentů v sekvenci výčtu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT Skip (   
   ULONG celt  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 celt  
 [in] Počet segmentů v pořadí výčtu pro přeskočení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí `S_FALSE` Pokud neexistují žádné další segmenty, které se mají přeskočit.  
  
## <a name="see-also"></a>Viz také  
 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)