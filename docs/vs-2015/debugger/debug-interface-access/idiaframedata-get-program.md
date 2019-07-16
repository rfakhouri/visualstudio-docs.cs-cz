---
title: IDiaFrameData::get_program | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::get_program method
ms.assetid: 9201409e-b4b1-4e2e-a9f8-d17678ac538b
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: d87f5c7fda25a901d44b9f511b9a92eb4471f845
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "68180004"
---
# <a name="idiaframedatagetprogram"></a>IDiaFrameData::get_program
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte řetězec program, který se používá k výpočtu do registru, nastavte před voláním na aktuální funkci.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_program (   
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí řetězec programu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Program řetězec je posloupnost makra, která je interpretován, aby bylo možné navázat prologu. Například typické zásobníku použít program řetězec `"$T0 $ebp = $eip $T0 4 + ^ = $ebp $T0 ^ = $esp $T0 8 + ="`. Formát je polština zpětného zápisu, ve kterém operátory následují operandy. `T0` představuje dočasné proměnné do zásobníku. V tomto příkladu provede následující kroky:  
  
1. Přesunout obsah registru `ebp` k `T0`.  
  
2. Přidat `4` s hodnotou v `T0` vytvářel adresu, získat hodnotu z této adresy a uložení hodnoty v registru `eip`.  
  
3. Získá hodnotu z adresu uloženou v `T0` a uložit do registru tuto hodnotu `ebp`.  
  
4. Přidat `8` s hodnotou v `T0` a uložit do registru tuto hodnotu `esp`.  
  
   Všimněte si, že je řetězec program konkrétním procesoru a konvence volání pro funkci reprezentované aktuální rámec zásobníku.  
  
## <a name="see-also"></a>Viz také  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
