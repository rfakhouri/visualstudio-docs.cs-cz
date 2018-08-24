---
title: Idiareadexeatoffsetcallback::readexecutableat – | Dokumentace Microsoftu
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
- IDiaReadExeAtOffsetCallback::ReadExecutableAt method
ms.assetid: 30b1cef0-b366-4712-8e89-d21f640964f8
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8202cb3ad7449d282e449fcfd8b284987c8f390d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42682000"
---
# <a name="idiareadexeatoffsetcallbackreadexecutableat"></a>IDiaReadExeAtOffsetCallback::ReadExecutableAt
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [idiareadexeatoffsetcallback::readexecutableat –](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idiareadexeatoffsetcallback-readexecutableat).  
  
Přečte zadaný počet bajtů počínaje od určeného posunutí ze spustitelného souboru.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
HRESULT ReadExecutableAt (   
   DWORDLONG fileOffset,  
   DWORD     cbData,  
   DWORD*    pcbData,  
   BYTE      data[]  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 fileOffset  
 [in] Posun ve spustitelném souboru má začínat čtení.  
  
 cbData  
 [in] Počet bajtů ke čtení.  
  
 pcbData  
 [out] Vrátí počet přečtených bajtů.  
  
 data]  
 [out v] Pole, které se vyplní přečtených ze souboru bajtů.  
  
## <a name="remarks"></a>Poznámky  
 Tato metoda je volána kód podpory, který DIA načtení bajtů dat ze spustitelného souboru pomocí posun absolutní. Tato metoda je volána z podporu [idiadatasource::loaddataforexe –](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md) metody.  
  
## <a name="see-also"></a>Viz také  
 [Idiareadexeatoffsetcallback –](../../debugger/debug-interface-access/idiareadexeatoffsetcallback.md)   
 [IDiaDataSource::loadDataForExe](../../debugger/debug-interface-access/idiadatasource-loaddataforexe.md)



