---
title: IDiaSymbol::get_isAcceleratorStubFunction | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: cc4ea375-76f6-4ba8-baed-c5fa82108137
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f6a7d2f27e776b37c392eb0116425ceeb6916031
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="idiasymbolgetisacceleratorstubfunction"></a>IDiaSymbol::get_isAcceleratorStubFunction
Určuje, zda je symbol odpovídá symbol nejvyšší úrovně funkce pro shaderu zkompilovaném pro akcelerátor, která odpovídá `parallel_for_each` volání.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_isAcceleratorStubFunction(   
   BOOL* pFlag);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pFlag`  
 [out] Ukazatel `BOOL` určující, zda je symbol odpovídá symbol nejvyšší úrovně funkce pro shaderu zkompilovaném pro akcelerátor, která odpovídá `parallel_for_each` volání.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`, jinak vrátí `S_FALSE` nebo chybový kód.  
  
## <a name="see-also"></a>Viz také  
 [Idiasymbol –](../../debugger/debug-interface-access/idiasymbol.md)