---
title: Scccheckout – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccCheckout
helpviewer_keywords:
- SccCheckout function
ms.assetid: 06e9ecd7-fc09-40c1-9dd1-2b56c622c80b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 728382594b1682f93ba1823558f3f9f02689be1b
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53955036"
---
# <a name="scccheckout-function"></a>Scccheckout – funkce
Zadaný seznam plně kvalifikovaných názvech, tato funkce rezervuje je na místním disku. Komentář se vztahuje na všechny soubory rezervován. Může být argumentem komentář `null` řetězec.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccCheckout (  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LPCSTR    lpComment,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
### <a name="parameters"></a>Parametry  
 pvContext  
 [in] Struktura kontext modulu plug-in zdroje ovládacího prvku.  
  
 hWnd  
 [in] Popisovač okna integrovaného vývojového prostředí, které modul plug-in správy zdrojového kódu můžete použít jako nadřazený pro všechna dialogová okna, které poskytuje.  
  
 %{nfiles/  
 [in] Počet vybraných rezervování souborů.  
  
 lpFileNames  
 [in] Pole úplná místní cesta názvy souborů, které mají být rezervován.  
  
 lpComment  
 [in] Komentář se má použít u všech vybraných souborů rezervuje.  
  
 fOptions  
 [in] Příkaz příznaky (viz [příznaky Bitflag používané konkrétními příkazy](../extensibility/bitflags-used-by-specific-commands.md)).  
  
 pvOptions  
 [in] Možností správy zdrojového kódu plug-konkrétní.  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Podívejte se na bylo úspěšné.|  
|SCC_E_FILENOTCONTROLLED|Vybraný soubor není pod správou zdrojového kódu.|  
|SCC_E_ACCESSFAILURE|Došlo k problému, přístup k systému správy zdrojového kódu, pravděpodobně kvůli problémům se síti nebo kolize. Doporučuje se zkuste to znovu.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže k provedení této operace.|  
|SCC_E_NONSPECIFICERROR|K nespecifikované chybě. Soubor nebyl zaregistrován.|  
|SCC_E_ALREADYCHECKEDOUT|Uživatel už má soubor rezervován.|  
|SCC_E_FILEISLOCKED|Soubor je uzamčen, zakazují vytváření nových verzí.|  
|SCC_E_FILEOUTEXCLUSIVE|Další uživatelé registraci nedokončí exkluzivní registrace u tohoto souboru.|  
|SCC_I_OPERATIONCANCELED|Operace byla zrušena před dokončením.|  
  
## <a name="see-also"></a>Viz také:  
 [Funkce modulu plug-in API zdrojového ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)   
 [Příznaky Bitflag používané konkrétními příkazy](../extensibility/bitflags-used-by-specific-commands.md)