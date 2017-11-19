---
title: "Idiainjectedsource::get_length – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaInjectedSource::get_length method
ms.assetid: 38b88b8b-c2e0-4b2d-8b8b-9ff373733e78
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a02439d05fd160fa73c843d85b27dee9f8a9f29c
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiainjectedsourcegetlength"></a>IDiaInjectedSource::get_length
Získá počet bajtů kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_length (   
   ULONGLONG* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí počet bajtů kódu.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Hodnota vrácená touto metodou je délka zdrojový kód a se stejnou hodnotu, jak ho vrátila [idiainjectedsource::get_source –](../../debugger/debug-interface-access/idiainjectedsource-get-source.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [Idiainjectedsource –](../../debugger/debug-interface-access/idiainjectedsource.md)   
 [Idiainjectedsource::get_source –](../../debugger/debug-interface-access/idiainjectedsource-get-source.md)