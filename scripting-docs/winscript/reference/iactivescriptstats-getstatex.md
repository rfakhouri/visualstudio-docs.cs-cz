---
title: IActiveScriptStats::GetStatEx | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: 824546b64323f7fb88c4ec016f8420169afa665c
ms.sourcegitcommit: 116e9614867e0b3c627ce9001012a4c39435a42b
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/08/2019
ms.locfileid: "54097328"
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
>  Tato metoda teď není implementovaná.  
  
## <a name="see-also"></a>Viz také  
 [IActiveScriptStats::GetStat](../../winscript/reference/iactivescriptstats-getstat.md)   
 [IActiveScriptStats – rozhraní](../../winscript/reference/iactivescriptstats-interface.md)