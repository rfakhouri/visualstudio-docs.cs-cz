---
title: Sccquerychanges – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccQueryChanges
helpviewer_keywords:
- SccQueryChanges function
ms.assetid: 4cd58eb3-6952-49b1-9620-8682e3eaa604
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: d6fabc1108f82c1cd2b43bf740e58c4ea9bb613e
ms.sourcegitcommit: 37fb7075b0a65d2add3b137a5230767aa3266c74
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/02/2019
ms.locfileid: "53910880"
---
# <a name="sccquerychanges-function"></a>SccQueryChanges – funkce
Tato funkce vytvoří výčet daný seznam files a poskytuje informace o změnách název pro každý soubor prostřednictvím funkce zpětného volání.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccQueryChanges(  
   LPVOID           pContext,  
   LONG             nFiles,  
   LPCSTR*          lpFileNames,  
   QUERYCHANGESFUNC pfnCallback,  
   LPVOID           pvCallerData  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pContext  
 [in] Ukazatel kontext modulu plug-in zdroje ovládacího prvku.  
  
 %{nfiles/  
 [in] Počet souborů v `lpFileNames` pole.  
  
 lpFileNames  
 [in] Pole názvy souborů, chcete-li získat informace.  
  
 pfnCallback  
 [in] Funkce zpětného volání, která se zavolá k názvu každého souboru v seznamu (viz [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md) podrobnosti).  
  
 pvCallerData  
 [in] Hodnota, která se předají beze změny funkci zpětného volání.  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Dotaz proces úspěšně dokončil.|  
|SCC_E_PROJNOTOPEN|Projekt nebyl otevřen ve správě zdrojového kódu.|  
|SCC_E_ACCESSFAILURE|Došlo k problému, přístup k systému správy zdrojového kódu, pravděpodobně kvůli problémům se síti nebo kolize.|  
|SCC_E_NONSPECIFICERROR|Došlo k neurčené nebo obecné chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Změny, která je dotazována pro mají obor názvů: konkrétně, přejmenování, přidávání a odebírání souboru.  
  
## <a name="see-also"></a>Viz také  
 [Funkce rozhraní API modulu Plug-in zdroje ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)   
 [QUERYCHANGESFUNC](../extensibility/querychangesfunc.md)   
 [Chybové kódy](../extensibility/error-codes.md)