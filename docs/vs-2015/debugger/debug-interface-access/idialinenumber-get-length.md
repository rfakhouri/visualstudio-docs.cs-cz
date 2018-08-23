---
title: Idialinenumber::get_length – | Dokumentace Microsoftu
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
- IDiaLineNumber::get_length method
ms.assetid: 2c55a6f7-4ef5-45fb-9fd1-d72deaaa2829
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6c2e30106b5f410e57f6dacd5cc2d91d88928588
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677318"
---
# <a name="idialinenumbergetlength"></a>IDiaLineNumber::get_length
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idialinenumber::get_length –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idialinenumber-get-length).  
  
Získá počet bajtů v bloku.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_length (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí počet bajtů v bloku.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Blok je délka zdrojový kód na řádku reprezentovaná [idialinenumber –](../../debugger/debug-interface-access/idialinenumber.md) objektu.  
  
## <a name="see-also"></a>Viz také  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)



