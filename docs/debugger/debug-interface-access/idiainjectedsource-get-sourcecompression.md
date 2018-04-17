---
title: Idiainjectedsource::get_sourcecompression – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaInjectedSource::get_sourceCompression method
ms.assetid: 854b142f-23a9-466c-bf7f-98e581d5abcd
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3e3a769dd41d9787a278c7a3f72c31efcbd8a445
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiainjectedsourcegetsourcecompression"></a>IDiaInjectedSource::get_sourceCompression
Načte indikátoru komprese zdroj použít.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_sourceCompression (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Vrátí indikátoru komprese zdroj použít. Hodnota 0 označuje, že byl použit žádný zdroj komprese.  
  
## <a name="return-value"></a>Návratová hodnota  
 V případě úspěchu vrátí `S_OK`. Vrátí `S_FALSE` -li tato vlastnost není podporována. Jinak vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Hodnota vrácená touto metodou je specifické pro kompilátor použít. Kompilátor může například použít délka běhu kódování nebo stylu Huffmanova komprese.  
  
## <a name="see-also"></a>Viz také  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)