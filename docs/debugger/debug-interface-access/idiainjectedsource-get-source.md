---
title: Idiainjectedsource::get_source – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaInjectedSource::get_source method
ms.assetid: 3c0b5386-321f-4f8f-85cc-e2ee7b4cc3d2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a923e323f4ca9dc7f661457add7665f8c136ae92
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53824454"
---
# <a name="idiainjectedsourcegetsource"></a>IDiaInjectedSource::get_source
Získá počet bajtů zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_source (   
   DWORD  cbData,  
   DWORD* pcbData,  
   BYTE   data[]  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cbData`  
 [in] Počet bajtů, který představuje velikost vyrovnávací paměti pro data.  
  
 `pcbData`  
 [out] Vrátí počet bajtů, který představuje počet bajtů vrácených. Pokud `data` je `NULL`, pak `pcbData` celkový počet bajtů dat je k dispozici.  
  
 `data[]`  
 [out] Vyrovnávací paměť, která se vyplní bajtů zdroje.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.  
  
## <a name="see-also"></a>Viz také  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)