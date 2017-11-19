---
title: "Idiasegment::get_virtualaddress – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaSegment::get_virtualAddress method
ms.assetid: 30073dd0-c864-4c4a-8863-80f243419f6c
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1d82eb98704fbf7f06ea31001985cfee8def2a4c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiasegmentgetvirtualaddress"></a>IDiaSegment::get_virtualAddress
Načte virtuální adresy (VA) začátku části.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_virtualAddress (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí VA počáteční části.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. Jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiasegment –](../../debugger/debug-interface-access/idiasegment.md)