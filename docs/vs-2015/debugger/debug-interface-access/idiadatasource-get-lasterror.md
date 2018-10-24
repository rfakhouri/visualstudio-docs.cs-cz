---
title: Idiadatasource::get_lasterror – | Dokumentace Microsoftu
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
- IDiaDataSource::get_lastError method
ms.assetid: cf08850b-8b75-4e8c-90bd-bd0214756f99
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 853d7177b3d2bae01eb140ce0ddb3046c49470f1
ms.sourcegitcommit: 240c8b34e80952d00e90c52dcb1a077b9aff47f6
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/23/2018
ms.locfileid: "49837838"
---
# <a name="idiadatasourcegetlasterror"></a>IDiaDataSource::get_lastError
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Načte název souboru pro poslední chyba načtení.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
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
  
```cpp#  
BSTR    fileName;  
HRESULT errorCode = pSource->get_lastError( &fileName );  
```  
  
## <a name="see-also"></a>Viz také  
 [IDiaDataSource](../../debugger/debug-interface-access/idiadatasource.md)



