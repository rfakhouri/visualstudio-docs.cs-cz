---
title: QUERYCHANGESFUNC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- QUERYCHANGESFUNC
helpviewer_keywords:
- QUERYCHANGESFUNC callback function
- QUERYCHANGESDATA structure
ms.assetid: 9d383e2c-eee1-4996-973a-0652d4c5951c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d1df5f21ffed27c45ebee6315fcc29ee1dcc8fa4
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31139806"
---
# <a name="querychangesfunc"></a>QUERYCHANGESFUNC
Toto je funkce zpětného volání používané [SccQueryChanges](../extensibility/sccquerychanges-function.md) operaci vytvoření výčtu kolekce názvů souborů a určit stav každého souboru.  
  
 `SccQueryChanges` Funkce je uveden seznam souborů a odkazy `QUERYCHANGESFUNC` zpětného volání. Modul plug-in správy zdroje přes daného seznamu zobrazí a poskytuje stav (prostřednictvím této zpětného volání) pro každý soubor v seznamu.  
  
## <a name="signature"></a>Podpis  
  
```cpp  
typedef BOOL (*QUERYCHANGESFUNC)(  
   LPVOID pvCallerData,  
   QUERYCHANGESDATA * pChangesData  
);  
```  
  
## <a name="parameters"></a>Parametry  
 pvCallerData  
 [v] `pvCallerData` Parametr předaný volající (IDE) [SccQueryChanges](../extensibility/sccquerychanges-function.md). Modul plug-in správy zdroje měli žádné předpoklady o obsahu této hodnoty.  
  
 pChangesData  
 [v] Ukazatel na [QUERYCHANGESDATA struktura](#LinkQUERYCHANGESDATA) struktura popisující změny do souboru.  
  
## <a name="return-value"></a>Návratová hodnota  
 Prostředí IDE vrátí odpovídající chybový kód:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Pokračujte ve zpracování.|  
|SCC_I_OPERATIONCANCELED|Zastavte zpracování.|  
|SCC_E_xxx|Všechny příslušné SCC chyby by se měla zastavit zpracování.|  
  
##  <a name="LinkQUERYCHANGESDATA"></a> Struktura QUERYCHANGESDATA  
 Struktura předaná pro každý soubor vypadá takto:  
  
```cpp  
struct QUERYCHANGESDATA_A  
{  
    DWORD  dwSize;  
    LPCSTR lpFileName;  
    DWORD  dwChangeType;  
    LPCSTR lpLatestName;  
};  
  
typedef struct QUERYCHANGESDATA_A QUERYCHANGESDATA;  
  
struct QUERYCHANGESDATA_W  
{  
    DWORD   dwSize;  
    LPCWSTR lpFileName;  
    DWORD   dwChangeType;  
    LPCWSTR lpLatestName;  
};  
```  
  
 dwSize  
 Velikost tuto strukturu (v bajtech).  
  
 lpFileName  
 Původní název souboru pro tuto položku.  
  
 dwChangeType  
 Kód označující stav souboru:  
  
|Kód|Popis|  
|----------|-----------------|  
|`SCC_CHANGE_UNKNOWN`|Nepodařilo se zjistit, co se změnilo.|  
|`SCC_CHANGE_UNCHANGED`|Žádné změny název pro tento soubor.|  
|`SCC_CHANGE_DIFFERENT`|Soubor s jinou identitu, ale v databázi existují se stejným názvem.|  
|`SCC_CHANGE_NONEXISTENT`|Soubor neexistuje v databázi nebo místně.|  
|`SCC_CHANGE_DATABASE_DELETED`|Soubor byl odstraněn v databázi.|  
|`SCC_CHANGE_LOCAL_DELETED`|Soubor byl odstraněn místně, ale soubor stále existuje v databázi. Pokud to nelze určit, vrátí `SCC_CHANGE_DATABASE_ADDED`.|  
|`SCC_CHANGE_DATABASE_ADDED`|Soubor přidáno do databáze, ale neexistuje místně.|  
|`SCC_CHANGE_LOCAL_ADDED`|Soubor neexistuje v databázi a je novou místní soubor.|  
|`SCC_CHANGE_RENAMED_TO`|Soubor přejmenovat nebo přesunout v databázi jako `lpLatestName`.|  
|`SCC_CHANGE_RENAMED_FROM`|Soubor přejmenovat nebo přesunout v databázi z `lpLatestName`; Pokud je to příliš nákladné chcete sledovat, vrátí různé příznak, jako například `SCC_CHANGE_DATABASE_ADDED`.|  
  
 lpLatestName  
 Aktuální název souboru pro tuto položku.  
  
## <a name="see-also"></a>Viz také  
 [Funkce zpětného volání, které implementují rozhraní IDE](../extensibility/callback-functions-implemented-by-the-ide.md)   
 [SccQueryChanges](../extensibility/sccquerychanges-function.md)   
 [Chybové kódy](../extensibility/error-codes.md)