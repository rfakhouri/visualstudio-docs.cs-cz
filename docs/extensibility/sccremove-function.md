---
title: Funkce SccRemove | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccRemove
helpviewer_keywords:
- SccRemove function
ms.assetid: 20830fdc-c0e9-4a5f-bf60-33f28874442f
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 71a79ac1b61b3f8f69d0698ead6fa3284fe37ce0
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="sccremove-function"></a>SccRemove – funkce
Tato funkce odstraní soubory ze správy zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccRemove(  
   LPVOID    pvContext,  
   HWND      hWnd,  
   LONG      nFiles,  
   LPCSTR*   lpFileNames,  
   LPCSTR    lpComment,  
   LONG      fOptions,  
   LPCMDOPTS pvOptions  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pvContext  
 [v] Struktura modulu plug-in kontextu řízení zdroje.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 : %{nfiles/  
 [v] Počet souborů zadaný v `lpFileNames` pole.  
  
 lpFileNames  
 [v] Pole úplná místní cesta názvy souborů, které se odeberou.  
  
 lpComment  
 [v] Komentář, který má být použita pro každý soubor, který je právě odebírán.  
  
 fOptions  
 [v] Příkaz příznaky (nepoužívané).  
  
 pvOptions  
 [v] Zdroj ovládacího prvku plug-konkrétní možnosti.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Odebrání bylo úspěšné.|  
|SCC_E_FILENOTCONTROLLED|Vybraný soubor není ve správě zdrojového kódu.|  
|SCC_E_OPNOTSUPPORTED|Správy zdrojového kódu nepodporuje tuto operaci.|  
|SCC_E_ISCHECKEDOUT|Soubor nelze odebrat, protože uživatel aktuálně je rezervována.|  
|SCC_E_ACCESSFAILURE|Došlo k chybě při přístupu správy zdrojového kódu, pravděpodobně kvůli problémům s sítě nebo kolizí.|  
|SCC_E_NOTAUTHORIZED|Uživatel nemůže provést tuto operaci.|  
|SCC_E_NONSPECIFICERROR|Nespecifikované chybě; Soubor nebyl odebrán.|  
|SCC_I_OPERATIONCANCELED|Operace byla zrušena před dokončením.|  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce odebere soubory ze správy zdrojového kódu, ale nedojde k jejich odstranění z místního pevného disku uživatele.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)