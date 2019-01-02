---
title: Idiasession::findfilebyid – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findFileById method
ms.assetid: 710efe04-78b5-4f3e-a1d8-f9b069063503
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: f92e811936e4ed7e8bc5e5272c22256f66fbf689
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53832843"
---
# <a name="idiasessionfindfilebyid"></a>IDiaSession::findFileById
Zkopíruje zdrojový soubor pomocí identifikátoru zdrojového souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findFileById (   
   DWORD            uniqueId,  
   IDiaSourceFile** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `uniqueId`  
 [in] Určuje identifikátor zdrojového souboru.  
  
 `ppResult`  
 [out] Vrátí [idiasourcefile –](../../debugger/debug-interface-access/idiasourcefile.md) načíst objekt, který reprezentuje zdrojový soubor.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Identifikátor zdrojového souboru je jedinečná hodnota používá interně ke DIA SDK, aby všechny zdrojové soubory jedinečný. Tato metoda se obvykle používá interně ke DIA SDK.  
  
## <a name="see-also"></a>Viz také  
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [Idiasession::FindFile –](../../debugger/debug-interface-access/idiasession-findfile.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)