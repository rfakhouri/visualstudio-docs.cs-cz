---
title: Sccrename – funkce | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- SccRename
helpviewer_keywords:
- SccRename function
ms.assetid: b467ade6-a1db-4c0b-b60f-7850ec4f79eb
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: cb3605dd27c00821e7920ba12d5d4ce9f2130bd2
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "54983713"
---
# <a name="sccrename-function"></a>SccRename – funkce
Tato funkce přejmenuje soubor v systému správy zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccRename(  
   LPVOID pvContext,  
   HWND   hWnd,  
   LPCSTR lpFileName,  
   LPCSTR lpNewName  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [in] Struktura kontext modulu plug-in zdroje ovládacího prvku.  
  
 hWnd  
 [in] Popisovač okna integrovaného vývojového prostředí, které modul plug-in správy zdrojového kódu můžete použít jako nadřazený pro všechna dialogová okna, které poskytuje.  
  
 lpFileName  
 [in] Plně kvalifikovaný název souboru se přejmenovat.  
  
 lpNewName  
 [in] Plně kvalifikovaný název nového. Pokud cesta k adresáři se liší, pak tento soubor se přesunul z jednoho podadresáře do jiného.  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Přejmenování operace byla úspěšně dokončena.|  
|SCC_E_PROJNOTOPEN|Projekt není otevřen v rámci správy zdrojového kódu.|  
|SCC_E_FILENOTCONTROLLED|Soubor není pod správou zdrojových kódů.|  
|SCC_E_ACCESSFAILURE|Došlo k problému, přístup k systému správy zdrojového kódu, pravděpodobně kvůli problémům se síti nebo kolize.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemá oprávnění k dokončení této operace.|  
|SCC_E_COULDNOTCREATEPROJECT|Projekt nejde vytvořit, protože část procesu přejmenování.|  
|SCC_E_OPNOTPERFORMED|Operace se neprovedla.|  
|SCC_E_NONSPECIFICERROR|Došlo k neurčené nebo obecné chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce slouží k přejmenování souboru nebo ji přesunout z jednoho umístění do druhého v systému správy zdrojového kódu. Modul plug-in správy zdrojového kódu by se neměly pokoušet získat přístup k souboru na disku. Je zodpovědností rozhraní IDE přejmenovat místní soubor.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)