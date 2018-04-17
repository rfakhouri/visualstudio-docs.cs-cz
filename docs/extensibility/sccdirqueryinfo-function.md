---
title: Funkce SccDirQueryInfo | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccDirQueryInfo
helpviewer_keywords:
- SccDirQueryInfo function
ms.assetid: 459e2d99-573d-47c4-b834-6d82c5e14162
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1de32b8502e40c953bd7080d64e56047e6bb5ce9
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="sccdirqueryinfo-function"></a>SccDirQueryInfo – funkce
Tato funkce prověří seznam plně kvalifikovaný adresářů pro jejich aktuální stav.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccDirQueryInfo(  
LPVOID  pContext,  
LONG    nDirs,  
LPCSTR* lpDirNames,  
LPLONG  lpStatus  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 nDirs  
 [v] Počet adresářů chcete zadat dotaz.  
  
 lpDirNames  
 [v] Pole úplné cesty adresáře, které chcete zadat dotaz.  
  
 lpStatus  
 [ve out] Strukturu pole pro modul plug-in vrátit příznaky stavu zdrojového kódu (viz [Directory stavový kód](../extensibility/directory-status-code-enumerator.md) podrobnosti).  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Dotaz byl úspěšný.|  
|SCC_E_OPNOTSUPPORTED|Systém správy zdrojového kódu nepodporuje tuto operaci.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí. Doporučuje se zkuste to znovu.|  
|SCC_E_NONSPECIFICERROR<br /><br /> SCC_E_UNKNOWNERROR|Došlo k nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Funkce vyplní celé pole návratový s bitová maska bitů z `SCC_DIRSTATUS` řady (v tématu [Directory stavový kód](../extensibility/directory-status-code-enumerator.md)), jeden záznam pro každý adresář zadaný. Stav pole je přidělena volající.  
  
 Prostředí IDE používá tuto funkci před adresář je přejmenován na zkontrolujte, zda adresář je ve správě zdrojového kódu pomocí dotazu, zda má odpovídající projektu. Pokud adresář není ve správě zdrojového kódu, rozhraní IDE pro správné upozornění uživatele.  
  
> [!NOTE]
>  Pokud není implementovat jednu nebo více hodnot stavu vybere modul plug-in správy zdroje, neimplementované bits měli nastavit na nulu.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [Directory stavový kód](../extensibility/directory-status-code-enumerator.md)