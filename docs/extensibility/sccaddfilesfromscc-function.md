---
title: Funkce SccAddFilesFromSCC | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccAddFilesFromSCC
helpviewer_keywords:
- SccAddFilesFromSCC function
ms.assetid: f21a3500-ade8-4dd8-8647-10e2179be9c1
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: dc42a7be878ce52f4d951171c6b5cb08e195d564
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
ms.locfileid: "31137856"
---
# <a name="sccaddfilesfromscc-function"></a>SccAddFilesFromSCC – funkce
Tato funkce přidá seznam souborů, od správy zdrojového kódu aktuálně otevřenou projektu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccAddFilesFromSCC(  
   LPVOID  pContext,  
   HWND    hWnd,  
   LPSTR   lpUser,  
   LPSTR   lpAuxProjPath,  
   LONG    cFiles,  
   LPCSTR* lpFilePaths,  
   LPCSTR  lpDestination,  
   LPCSTR  lpComment,  
   LPBOOL  pbResults  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pContext  
 [v] Ukazatel modulu plug-in kontextu zdroj ovládacího prvku.  
  
 hWnd  
 [v] Obslužná rutina do okna IDE, modul plug-in správy zdroje můžete použít jako nadřazený objekt pro všechna dialogová okna poskytuje.  
  
 lpUser  
 [ve out] Uživatelské jméno (až SCC_USER_SIZE, včetně null ukončovací znak).  
  
 lpAuxProjPath  
 [ve out] Pomocná řetězec identifikující projektu (až `SCC_PRJPATH_`velikost, včetně null ukončovací znak).  
  
 cFiles  
 [v] Počet souborů, které poskytují `lpFilePaths`.  
  
 lpFilePaths  
 [ve out] Pole názvy souborů pro přidání do aktuálního projektu.  
  
 lpDestination  
 [v] Cílovou cestu, kde jsou soubory k zapsání.  
  
 lpComment  
 [v] Komentář, který má být použita pro každý ze souborů, který chcete přidat.  
  
 pbResults  
 [ve out] Pole příznaky, které jsou sady, čímž indikuje úspěšné provedení (nenulové hodnoty nebo TRUE) nebo selhání (nula nebo FALSE) pro každý soubor (velikost pole musí být alespoň `cFiles` dlouho).  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_E_PROJNOTOPEN|Projekt není otevřené.|  
|SCC_E_OPNOTPERFORMED|Připojení není do stejné projektu podle specifikace `lpAuxProjPath.`|  
|SCC_E_NOTAUTHORIZED|Uživatel nemá oprávnění k aktualizaci databáze.|  
|SCC_E_NONSPECIFICERROR|Došlo k neznámé chybě.|  
|SCC_I_RELOADFILE|Musí být znovu načíst soubor nebo projektu.|  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu plug-in správy zdrojového kódu v rozhraní API](../extensibility/source-control-plug-in-api-functions.md)