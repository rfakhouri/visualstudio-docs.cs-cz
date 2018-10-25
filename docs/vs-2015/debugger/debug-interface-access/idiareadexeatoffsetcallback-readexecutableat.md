---
title: Idiareadexeatoffsetcallback::readexecutableat – | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
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
ms.openlocfilehash: 250fa60ec1564b87ccc561400e8b378619e9e850
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49930918"
---
# <a name="idiareadexeatoffsetcallbackreadexecutableat"></a>IDiaReadExeAtOffsetCallback::ReadExecutableAt
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

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



