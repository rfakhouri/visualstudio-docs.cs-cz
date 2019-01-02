---
title: Idialoadcallback2::restrictsystemrootaccess – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaLoadCallback2::RestrictSystemRootAccess method
ms.assetid: 39f22db8-632a-4ef0-babc-23f758e6d937
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 340e6a8cffbf681bb9e976664ccbbe15e6b00786
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53918722"
---
# <a name="idialoadcallback2restrictsystemrootaccess"></a>IDiaLoadCallback2::RestrictSystemRootAccess
Určuje, jestli hledání souborů PDB je povolený v kořenovém adresáři systému.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT RestrictSystemRootAccess();  
```  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="remarks"></a>Poznámky  
 Žádné jiné než návratový kód `S_OK` zabrání vyhledávání kořenový adresář pro soubory typu .pdb.  
  
## <a name="see-also"></a>Viz také  
 [IDiaLoadCallback2](../../debugger/debug-interface-access/idialoadcallback2.md)