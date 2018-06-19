---
title: IActiveScriptAuthor::GetInfoFromContext | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
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
ms.openlocfilehash: 27c13dbe51bb1150554275b5fbeacd00be2e445f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/27/2017
ms.locfileid: "24793332"
---
# <a name="iactivescriptauthorgetinfofromcontext"></a>IActiveScriptAuthor::GetInfoFromContext
Vrátí typ informace a pozice ukotvení pro daného znaku v bloku kódu. To poskytuje informace pro člen, IntelliSense, globálních seznamů a tipy pro parametr.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
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
 [v] Adresa řetězce bloku kódu sloužící ke generování výsledků informace.  
  
 `cchCode`  
 [v] Délka bloku kódu.  
  
 `ichCurrentPosition`  
 [v] Znak na pozici relativně ke spuštění bloku.  
  
 `dwListTypesRequested`  
 [v] Typy seznamu požadovaný. Může být kombinací následujícího:  
  
|Konstanta|Hodnota|Popis|  
|--------------|-----------|-----------------|  
|SCRIPT_CMPL_NOLIST|0x0000|Žádný seznam.|  
|SCRIPT_CMPL_MEMBERLIST|0x0001|Seznam členů.|  
|SCRIPT_CMPL_ENUMLIST|0x0002|Seznam výčtu.|  
|SCRIPT_CMPL_PARAMLIST|0x0004|Volání metody seznam parametrů.|  
|SCRIPT_CMPL_GLOBALLIST|0x0008|Globální seznam.|  
  
 Typ SCRIPT_CMPL_GLOBALLIST považován za výchozí položku dokončení, které mohou být kombinovány pomocí operátoru OR další položky dokončení. Skript pro tvorbu modul nejprve pokusí k naplnění informací o typu pro ostatní položky seznamu dokončení. Pokud to nepomůže, naplní se modul pro SCRIPT_CMPL_GLOBALLIST.  
  
 `pdwListTypesProvided`  
 [out] Typ seznamu zadaný.  
  
 `pichListAnchorPosition`  
 [out] Počáteční index kontext, který obsahuje aktuální pozici. Počáteční index je relativní vzhledem ke spuštění bloku.  
  
 To je vyplněno pouze tehdy, když `dwListTypesRequested` zahrnuje SCRIPT_CMPL_MEMBERLIST, SCRIPT_CMPL_ENUMLIST nebo SCRIPT_CMPL_GLOBALLIST. Pro ostatní typy požadovaný seznam výsledek není definován.  
  
 `pichFuncAnchorPosition`  
 [out] Počáteční index volání funkce, která obsahuje aktuální pozici. Počáteční index je relativní vzhledem ke spuštění bloku.  
  
 To je vyplněný, pouze když kontext, který obsahuje aktuální pozici volání funkce a při `dwListTypesRequested` zahrnuje SCRIPT_CMPL_PARAMLIST. Výsledek, jinak hodnota není definován.  
  
 `pmemid`  
 [out] MEMBERID funkce, podle definice typu v `IProvideMultipleClassInfo``ppunk` vnější parametr.  
  
 To je vyplněno pouze tehdy, když `dwListTypesRequested` zahrnuje SCRIPT_CMPL_PARAMLIST.  
  
 `piCurrentParameter`  
 [out] Index parametr, který obsahuje aktuální pozici. Pokud aktuální pozici na název funkce, se vrátí hodnotu -1.  
  
 `piCurrentParameter` Hodnota je vyplněný, pouze pokud `dwListTypesRequested` zahrnuje SCRIPT_CMPL_PARAMLIST.  
  
 `ppunk`  
 Informace o typu, který je zahrnutý ve formě `IProvideMultipleClassInfo` objektu.  
  
## <a name="return-value"></a>Návratová hodnota  
 `HRESULT`. Možné hodnoty zahrnují hodnoty v následující tabulce, ale nejsou na ně omezeny.  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|`S_OK`|Metoda byla úspěšná.|  
  
## <a name="remarks"></a>Poznámky  
  
## <a name="see-also"></a>Viz také  
 [IProvideMultipleClassInfo rozhraní](https://msdn.microsoft.com/library/microsoft.visualstudio.ole.interop.iprovidemultipleclassinfo.aspx)   
 [Iactivescriptauthor – rozhraní](../../winscript/reference/iactivescriptauthor-interface.md)