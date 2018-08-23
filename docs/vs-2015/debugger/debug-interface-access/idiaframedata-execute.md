---
title: Idiaframedata::Execute – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
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
- IDiaFrameData::execute method
ms.assetid: 7a6c7d03-1ff1-4059-bd54-5f407eeebc26
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d1f76bf5e5ef30c748f310e6a8a610035b7c08bb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42666498"
---
# <a name="idiaframedataexecute"></a>IDiaFrameData::execute
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiaframedata::Execute –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaframedata-execute).  
  
Provádí odvíjení zásobníku a vrátí výsledky v rozhraní rámce zásobníku funkce walk.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT execute (   
   IDiaStackWalkFrame* frame  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `frame`  
 [in] [Idiastackwalkframe –](../../debugger/debug-interface-access/idiastackwalkframe.md) objekt, který obsahuje stav rámce registrů.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby. V následující tabulce jsou uvedeny možné návratové hodnoty pro tuto metodu.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|E_DIA_INPROLOG|Nelze spustit blok zásobníku v kódu prologu.|  
|E_DIA_SYNTAX|Analyzovat v aplikaci rámce došlo k chybě.|  
|E_DIA_FRAME_ACCESS|Nepovedlo se přístup registrů nebo paměti.|  
|E_DIA_VALUE|Při výpočtu hodnoty (například dělení nulou).|  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána při ladění k provedení operace unwind zásobníku. [Idiastackwalkframe –](../../debugger/debug-interface-access/idiastackwalkframe.md) objektu je implementováno klientské aplikace pro příjem aktualizací registry a poskytovat metody používané `execute` metody.  
  
## <a name="see-also"></a>Viz také  
 [Idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)



