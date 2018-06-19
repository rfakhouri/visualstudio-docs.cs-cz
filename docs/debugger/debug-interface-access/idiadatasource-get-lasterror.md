---
title: Idiadatasource::get_lasterror – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaDataSource::get_lastError method
ms.assetid: cf08850b-8b75-4e8c-90bd-bd0214756f99
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 08d17e0532d4d5d987d69afa7de062a193371950
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/18/2018
ms.locfileid: "31457290"
---
# <a name="idiadatasourcegetlasterror"></a>IDiaDataSource::get_lastError
Načte název souboru pro poslední chyba zatížení.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT get_lastError (  
   BSTR* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pRetVal  
 [out] Vrátí řetězec, který obsahuje název souboru PDB spojený s poslední chyba zatížení.  
  
## <a name="return-value"></a>Návratová hodnota  
 Vrátí poslední kód chyby způsobené operace načtení. Vrátí `E_INVALIDARG` Pokud `pRetVal` parametr `NULL`.  
  
## <a name="example"></a>Příklad  
  
```C++  
BSTR    fileName;  
HRESULT errorCode = pSource->get_lastError( &fileName );  
```  
  
## <a name="see-also"></a>Viz také  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)