---
title: Idiaframedata::Execute – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaFrameData::execute method
ms.assetid: 7a6c7d03-1ff1-4059-bd54-5f407eeebc26
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0645d2364712769a6b4f18ef14fbbcb503a51888
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
---
# <a name="idiaframedataexecute"></a>IDiaFrameData::execute
Provede uvolnění zásobníku a vrátí výsledky v rozhraní procházení rámce zásobníku.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT execute (   
   IDiaStackWalkFrame* frame  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `frame`  
 [v] [Idiastackwalkframe –](../../debugger/debug-interface-access/idiastackwalkframe.md) objekt, který obsahuje stav rámce registrů.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby. V následující tabulce jsou uvedeny možné návratové hodnoty pro tuto metodu.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|E_DIA_INPROLOG|Rámec zásobníku v kódu prologu nelze provést.|  
|E_DIA_SYNTAX|Došlo k chybě došlo v programu rámce analýzy.|  
|E_DIA_FRAME_ACCESS|Nelze přístup registry nebo paměti.|  
|E_DIA_VALUE|Při výpočtu hodnoty (například dělení nulou).|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána při ladění do unwind zásobníku. [Idiastackwalkframe –](../../debugger/debug-interface-access/idiastackwalkframe.md) objektu je implementováno modulem klientská aplikace pro příjem aktualizací registry a pro poskytování metod používaných `execute` metoda.  
  
## <a name="see-also"></a>Viz také  
 [Idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)