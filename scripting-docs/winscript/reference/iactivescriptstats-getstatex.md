---
title: IActiveScriptStats::GetStatEx | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptStats.GetStatEx
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptStats::GetStatEx
ms.assetid: f526f51d-8ab5-49ef-a8f7-ae0ac1cb46e4
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3e5f25887d8fdd5b5fb774cc2e8619c1a93432c1
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63442780"
---
# <a name="iactivescriptstatsgetstatex"></a>IActiveScriptStats::GetStatEx
Vrátí statistiku pro vlastní skripty.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetStatEx(  
   REFGUID  guid,  
   ULONG*   pluHi,  
   ULONG*   pluLo  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `guid`  
 [in] Určuje, které statistiku k vrácení. Sémantika statistiky, které odpovídá konkrétní identifikátor GUID je zcela modul definované.  
  
 `pluHi`  
 [out] Vysoká 32 bitů 64bitové celé číslo bez znaménka představující statistiky.  
  
 `pluLo`  
 [out] Nízká 32 bitů 64bitové celé číslo bez znaménka představující statistiky.  
  
## <a name="return-value"></a>Návratová hodnota  
 Metoda vrátí `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
|`E_NOTIMPL`|Metoda není implementována.|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda umožňuje vlastní skriptovací stroj vrátit smysluplné statistiky pro vlastního hostitele.  
  
> [!NOTE]
> Tato metoda teď není implementovaná.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptStats::GetStat](../../winscript/reference/iactivescriptstats-getstat.md)   
 [IActiveScriptStats – rozhraní](../../winscript/reference/iactivescriptstats-interface.md)