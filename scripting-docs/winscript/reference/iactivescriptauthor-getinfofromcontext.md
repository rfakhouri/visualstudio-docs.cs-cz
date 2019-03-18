---
title: IActiveScriptAuthor::GetInfoFromContext | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IActiveScriptAuthor.GetInfoFromContext
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::GetInfoFromContext
ms.assetid: 9891b095-6eb5-4473-87c0-c2e5cd2afc1a
caps.latest.revision: 15
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e4fe885e116019608dd8d748c3cbdaff5d31dd2a
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58154410"
---
# <a name="iactivescriptauthorgetinfofromcontext"></a>IActiveScriptAuthor::GetInfoFromContext
Vrátí zadejte informace a pozice ukotvení pro daný znak do bloku kódu. To poskytuje informace pro člena, technologie IntelliSense, globální seznamy a tipy pro parametr.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT GetInfoFromContext(  
   LPCOLESTR  pszCode,  
   ULONG      cchCode,  
   ULONG      ichCurrentPosition,  
   DWORD      dwListTypesRequested,  
   DWORD      *pdwListTypesProvided,  
   ULONG      *pichListAnchorPosition,  
   ULONG      *pichFuncAnchorPosition,  
   MEMBERID   *pmemid,  
   LONG       *piCurrentParameter,  
   IUnknown   **ppunk  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pszCode`  
 [in] Adresa řetězec bloku kódu sloužícího ke generování informace výsledky.  
  
 `cchCode`  
 [in] Délka bloku kódu.  
  
 `ichCurrentPosition`  
 [in] Pozice znaku vzhledem k začátku bloku.  
  
 `dwListTypesRequested`  
 [in] Typy seznamů požadavku. Může být kombinací následujícího:  
  
|Konstanta|Hodnota|Popis|  
|--------------|-----------|-----------------|  
|SCRIPT_CMPL_NOLIST|0x0000|Žádný seznam.|  
|SCRIPT_CMPL_MEMBERLIST|0x0001|Seznam členů.|  
|SCRIPT_CMPL_ENUMLIST|0x0002|Seznam výčtu.|  
|SCRIPT_CMPL_PARAMLIST|0x0004|Seznam parametrů metody volání.|  
|SCRIPT_CMPL_GLOBALLIST|0x0008|Globální seznam.|  
  
 Typ SCRIPT_CMPL_GLOBALLIST je považován za výchozí dokončení položky, kterou můžete kombinovat pomocí operátoru OR s ostatními položkami dokončení. Skript, modul pro vytváření nejdřív pokusí k naplnění informací o typu pro jiné položky seznamu dokončení. Pokud se to nepodaří, naplní se modul pro SCRIPT_CMPL_GLOBALLIST.  
  
 `pdwListTypesProvided`  
 [out] Typ seznamu.  
  
 `pichListAnchorPosition`  
 [out] Počáteční index, který obsahuje aktuální pozici kontextu. Počáteční index je relativní vzhledem k začátku bloku.  
  
 To je vyplněný pouze tehdy, když `dwListTypesRequested` SCRIPT_CMPL_MEMBERLIST, SCRIPT_CMPL_ENUMLIST nebo SCRIPT_CMPL_GLOBALLIST. U jiných typů požadovaný seznam výsledek nedefinován.  
  
 `pichFuncAnchorPosition`  
 [out] Počáteční index, který obsahuje aktuální pozici volání funkce. Počáteční index je relativní vzhledem k začátku bloku.  
  
 To je vyplněný pouze v případě volání funkce je kontext, který obsahuje aktuální pozici a když `dwListTypesRequested` zahrnuje SCRIPT_CMPL_PARAMLIST. V opačném případě výsledek není definován.  
  
 `pmemid`  
 [out] MEMBERID funkci, jak je definováno podle typu ve službě `IProvideMultipleClassInfo``ppunk` výstupní parametr.  
  
 To je vyplněný pouze tehdy, když `dwListTypesRequested` zahrnuje SCRIPT_CMPL_PARAMLIST.  
  
 `piCurrentParameter`  
 [out] Index parametru, který obsahuje aktuální pozici. Pokud je aktuální pozice na název funkce, je vrácena hodnota -1.  
  
 `piCurrentParameter` Hodnota se vyplní pouze tehdy, když `dwListTypesRequested` zahrnuje SCRIPT_CMPL_PARAMLIST.  
  
 `ppunk`  
 Informace o typu, který je k dispozici ve formě `IProvideMultipleClassInfo` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [IProvideMultipleClassInfo Interface](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.ole.interop.iprovidemultipleclassinfo)   
 [IActiveScriptAuthor – rozhraní](../../winscript/reference/iactivescriptauthor-interface.md)