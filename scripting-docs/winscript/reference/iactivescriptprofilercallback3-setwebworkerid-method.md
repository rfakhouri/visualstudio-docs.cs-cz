---
title: Iactivescriptprofilercallback3::setwebworkerid – metoda | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 47744746-1276-441e-ab60-2a78f550e8e2
caps.latest.revision: 3
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0798a23b4c8ad4e5859bec73ebfed47a56b322d6
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "62993100"
---
# <a name="iactivescriptprofilercallback3setwebworkerid-method"></a>IActiveScriptProfilerCallback3::SetWebWorkerId – metoda
Upozornění profileru o ID pracovního procesu má použít pro tuto relaci profilování. Pokud funkce není prováděna v kontextu stránky, není tato metoda vyvolána. Hodnota `webWorkerId` zvýší o 1 pro každý pracovního procesu začínající hodnotou 1. ID hodnoty nemají stabilní nad rámec relaci, a pouze odpovídají pořadí, ve kterém byly vytvořeny zaměstnanců.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT SetWebWorkerId([in] DWORD webWorkerId);  
```  
  
#### <a name="parameters"></a>Parametry  
 `webWorkerId`  
 ID webového pracovního procesu.  
  
## <a name="return-value"></a>Návratová hodnota  
 Skriptovací modul se ignoruje vrácenou hodnotu této metody.