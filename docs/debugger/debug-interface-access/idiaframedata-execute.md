---
title: "Idiaframedata::Execute – | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaFrameData::execute method
ms.assetid: 7a6c7d03-1ff1-4059-bd54-5f407eeebc26
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 29b284e466ce751e86f488203b4b22c0c18c6573
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
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
 [Idiastackwalkframe –](../../debugger/debug-interface-access/idiastackwalkframe.md)