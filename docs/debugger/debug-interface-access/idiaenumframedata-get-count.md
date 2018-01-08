---
title: "Idiaenumframedata::get_count – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaEnumFrameData::get_Count method
ms.assetid: 94374d27-e335-4e90-a442-233181ab8e58
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 080224e933ef89ad207b86eb0e1bf8b2a77adcd3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiaenumframedatagetcount"></a>IDiaEnumFrameData::get_Count
Získá počet elementů datové rámce.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_Count (   
   LONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pRetVal  
 [out] Vrátí počet datových elementů rámce.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumframedata –](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaEnumFrameData::Item](../../debugger/debug-interface-access/idiaenumframedata-item.md)