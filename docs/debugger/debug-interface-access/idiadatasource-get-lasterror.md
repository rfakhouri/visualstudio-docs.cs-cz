---
title: Idiadatasource::get_lasterror – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::get_lastError method
ms.assetid: cf08850b-8b75-4e8c-90bd-bd0214756f99
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2dfb9968aac05c9bbe79de1d37b13eb03dd31714
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54972807"
---
# <a name="idiadatasourcegetlasterror"></a>IDiaDataSource::get_lastError
Načte název souboru pro poslední chyba načtení.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_lastError (  
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pRetVal  
 [out] Vrátí řetězec, který obsahuje název souboru PDB přidružené k poslední chyba načtení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí poslední kód chyby způsobené operace načtení. Vrátí `E_INVALIDARG` Pokud `pRetVal` parametr `NULL`.  
  
## <a name="example"></a>Příklad  
  
```C++  
BSTR    fileName;  
HRESULT errorCode = pSource->get_lastError( &fileName );  
```  
  
## <a name="see-also"></a>Viz také  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)