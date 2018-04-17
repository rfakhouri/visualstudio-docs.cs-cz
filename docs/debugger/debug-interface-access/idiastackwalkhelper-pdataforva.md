---
title: IDiaStackWalkHelper::pdataForVA | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::pdataByVA method
ms.assetid: fafc38fe-74dc-4726-9a51-eebf3a673d7f
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 42b38aa37260f7ffe7cf0a64ea5199de5253a97f
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiastackwalkhelperpdataforva"></a>IDiaStackWalkHelper::pdataForVA
Vrátí přidružený virtuální adresu PDATA datového bloku.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT pdataForVA(   
   ULONGLONG  va,  
   DWORD      cbData,  
   DWORD*     pcbData,  
   BYTE*      pbData  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `va`  
 [v] Určuje adresu virtuální dat získat.  
  
 `cbData`  
 [v] Velikost dat v bajtech získat.  
  
 `pcbData`  
 [out] Vrátí skutečná velikost dat v bajtech, které byl získán.  
  
 `pbData`  
 [ve out] Vyrovnávací paměť, která obsahuje požadovaná data. Nemůže být `NULL`.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` Pokud neexistuje žádné PDATA zadané adresy. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 PDATA (části s názvem ".pdata") z kompilace obsahuje informace o zpracování výjimek pro funkce.  
  
 Volající ví, kolik dat má být vrácen, takže není nutné požádat, kolik dat je k dispozici má volající. Proto je přijatelné pro implementace této metody vrátit chybu, pokud `pbData` parametr `NULL`.  
  
## <a name="see-also"></a>Viz také  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)