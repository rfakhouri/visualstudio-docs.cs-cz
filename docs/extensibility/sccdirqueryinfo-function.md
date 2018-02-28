---
title: Funkce SccDirQueryInfo | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccDirQueryInfo
helpviewer_keywords:
- SccDirQueryInfo function
ms.assetid: 459e2d99-573d-47c4-b834-6d82c5e14162
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: c7a930c0fcdffbc76bba431012d76dd6d13686d0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
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