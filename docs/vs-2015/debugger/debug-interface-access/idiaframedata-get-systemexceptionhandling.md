---
title: Idiaframedata::get_systemexceptionhandling – | Dokumentace Microsoftu
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
- IDiaFrameData::get_systemExceptionHandling method
ms.assetid: e8df1972-913c-446c-9779-775575b0caa9
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bf31d69f51e5182d6fb211a0936ba089eb4137ef
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631419"
---
# <a name="idiaframedatagetsystemexceptionhandling"></a>IDiaFrameData::get_systemExceptionHandling
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiaframedata::get_systemexceptionhandling –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiaframedata-get-systemexceptionhandling).  
  
Získá příznak, který určuje, zda systém zpracování výjimek je v platnosti.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT get_systemExceptionHandling (   
   BOOL* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pRetVal  
 [out] Vrátí `TRUE` pokud zpracování výjimek systému je v platnosti; v opačném případě vrátí `FALSE`.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. V opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Zpracování výjimek systému se běžně označuje jako strukturované zpracování výjimek.  
  
 Chcete-li zjistit, zda zpracování výjimek jazyka C++ je v platnosti, zavolejte [idiaframedata::get_cplusplusexceptionhandling –](../../debugger/debug-interface-access/idiaframedata-get-cplusplusexceptionhandling.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [Idiaframedata –](../../debugger/debug-interface-access/idiaframedata.md)   
 [IDiaFrameData::get_cplusplusExceptionHandling](../../debugger/debug-interface-access/idiaframedata-get-cplusplusexceptionhandling.md)



