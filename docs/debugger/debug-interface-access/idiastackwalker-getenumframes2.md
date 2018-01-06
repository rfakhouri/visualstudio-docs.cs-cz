---
title: IDiaStackWalker::getEnumFrames2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: IDiaStackWalker2::getEnumFrames2 method
ms.assetid: 73196d3f-112c-4b3a-997b-7c6b815d4afc
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 85e003259f5a9f04a83f5a46433001fad12b6711
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="idiastackwalkergetenumframes2"></a>IDiaStackWalker::getEnumFrames2
Načte enumerátor rámce zásobníku pro konkrétní platformu typu.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
  
      HRESULT getEnumFrames2(   
   enum  CV_CPU_TYPE_e    cpuid,  
   IDiaStackWalkHelper*   pHelper,  
   IDiaEnumStackFrames**  ppEnum  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `cpuid`  
 [v] Hodnota z [CV_CPU_TYPE_e – výčet](../../debugger/debug-interface-access/cv-cpu-type-e.md) výčtu zadání typu platformy.  
  
 `pHelper`  
 [v] Pomocné rutiny [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md) objektu.  
  
 `ppEnum`  
 [out] Vrátí [idiaenumstackframes –](../../debugger/debug-interface-access/idiaenumstackframes.md) objekt obsahující seznam [idiastackframe –](../../debugger/debug-interface-access/idiastackframe.md) objekty.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 K získání seznamu rámce zásobníku pro právě x86 platformy, volání [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md) metoda.  
  
## <a name="see-also"></a>Viz také  
 [Idiastackwalker –](../../debugger/debug-interface-access/idiastackwalker.md)   
 [CV_CPU_TYPE_e – výčet](../../debugger/debug-interface-access/cv-cpu-type-e.md)   
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [Idiastackframe –](../../debugger/debug-interface-access/idiastackframe.md)   
 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)