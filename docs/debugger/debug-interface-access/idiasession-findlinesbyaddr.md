---
title: Idiasession::findlinesbyaddr – | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findLinesByAddr method
ms.assetid: 640403c0-14cf-403c-ad19-38b3bdc28ca8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a64868b8bbf92f2c11faeb2b0890c6cd4893941f
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54951557"
---
# <a name="idiasessionfindlinesbyaddr"></a>IDiaSession::findLinesByAddr
Načte řádky v zadané kompilace, které obsahují zadané adrese.  
  
## <a name="syntax"></a>Syntaxe  
  
```C++  
HRESULT findLinesByAddr (   
   DWORD                 seg,  
   DWORD                 offset,  
   DWORD                 length,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `seg`  
 [in] Určuje komponentu části z konkrétní adresy.  
  
 `offset`  
 [in] Určuje posunutí komponentu konkrétní adresu.  
  
 `length`  
 [in] Určuje počet bajtů rozsah adres, aby pokryl s Tento dotaz.  
  
 `ppResult`  
 [out] Vrátí [idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md) objekt, který obsahuje seznam všech řádku čísla tohoto krytí zadaný rozsah adres.  
  
## <a name="return-value"></a>Návratová hodnota  
 Pokud je úspěšná, vrátí `S_OK`; v opačném případě vrátí kód chyby.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje funkci, která získá všechna čísla řádků, které jsou obsažené ve funkci pomocí funkce adresu a délku.  
  
```C++  
IDiaEnumLineNumbers* GetLineNumbersByAddr(IDiaSymbol *pFunc,  
                                          IDiaSession *pSession)  
{  
    IDiaEnumLineNumbers* pEnum = NULL;  
    DWORD                seg;  
    DWORD                offset;  
    ULONGLONG            length;  
  
    if (pFunc->get_addressSection ( &seg ) == S_OK &&  
        pFunc->get_addressOffset ( &offset ) == S_OK)  
    {  
        pFunc->get_length ( &length );  
        pSession->findLinesByAddr( seg, offset, static_cast<DWORD>( length ), &pEnum );  
    }  
    return(pEnum);  
}  
```  
  
## <a name="see-also"></a>Viz také  
 [Idiaenumlinenumbers –](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [Idiasession –](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSession::findLinesByVA](../../debugger/debug-interface-access/idiasession-findlinesbyva.md)