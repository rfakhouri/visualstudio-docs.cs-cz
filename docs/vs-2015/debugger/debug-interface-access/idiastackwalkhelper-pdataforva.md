---
title: IDiaStackWalkHelper::pdataForVA | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalkHelper2::pdataByVA method
ms.assetid: fafc38fe-74dc-4726-9a51-eebf3a673d7f
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ebde960d8539ef23946e29b0af707cf2b1f47a91
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49180502"
---
# <a name="idiastackwalkhelperpdataforva"></a>IDiaStackWalkHelper::pdataForVA
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Vrátí přidružený virtuální adresu PDATA datového bloku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT pdataForVA(   
   ULONGLONG  va,  
   DWORD      cbData,  
   DWORD*     pcbData,  
   BYTE*      pbData  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `va`  
 [in] Určuje virtuální adresu dat, která poskytuje.  
  
 `cbData`  
 [in] Velikost dat v bajtech získat.  
  
 `pcbData`  
 [out] Vrátí skutečný objem dat v bajtech, ke které byl získán.  
  
 `pbData`  
 [out v] Vyrovnávací paměť je vyplní požadovaná data. Nemůže být `NULL`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` Pokud neexistuje žádný PDATA pro zadanou adresu. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 PDATA (oddíl s názvem ".pdata") kompilace obsahuje informace o zpracování výjimek pro funkce.  
  
 Volající ví, kolik dat má být vrácen tak má volající není potřeba zeptejte, kolik dat je k dispozici. Proto je přijatelné pro implementace této metody vrátit chybu, pokud `pbData` parametr `NULL`.  
  
## <a name="see-also"></a>Viz také  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)



