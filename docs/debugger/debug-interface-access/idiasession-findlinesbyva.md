---
title: Idiasession::findlinesbyva – | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLinesByVA method
ms.assetid: f647eee9-a73c-483b-9fe9-21f42e560a7b
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6d9864114820859486ab6b1bfd1700f75496b1f9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="idiasessionfindlinesbyva"></a>IDiaSession::findLinesByVA
Načte informace číslo řádku pro řádky, které jsou obsaženy v rozsahu zadané virtuální adresy (VA).  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findLinesByVA (   
   ULONGLONG             va,  
   DWORD                 length,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `va`  
 [v] Určuje adresu jako VA.  
  
 `length`  
 [v] Určuje počet bajtů rozsah adres tak, aby pokrývalo k tomuto dotazu.  
  
 `ppResult`  
 [out] Vrátí [idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md) objekt, který obsahuje seznam všech řádku čísla tohoto krytí zadaný rozsah adres.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje funkce, který získá všechna čísla řádků obsažené ve funkci pomocí funkce virtuální adresy a délka.  
  
```C++  
IDiaEnumLineNumbers *GetLineNumbersByVA(IDiaSymbol *pFunc, IDiaSession *pSession)  
{  
    IDiaEnumLineNumbers* pEnum = NULL;  
    ULONGLONG            va;  
    ULONGLONG            length;  
  
    if (pFunc->get_virtualAddress ( &va ) == S_OK)  
    {  
        pFunc->get_length( &length );  
        pSession->findLinesByVA( va, static_cast<DWORD>( length ), &pEnum );  
    }  
    return(pEnum);  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)