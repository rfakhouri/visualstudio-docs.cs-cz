---
title: Sccenumchangedfiles – funkce | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccEnumChangedFiles
helpviewer_keywords:
- SccEnumChangedFiles function
ms.assetid: 76cac510-107b-4c1a-ba60-9c39b6db2e71
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5b8fb9c83d8948ca3edc0650e85af6ea8c011abc
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/08/2018
ms.locfileid: "39639825"
---
# <a name="sccenumchangedfiles-function"></a>Sccenumchangedfiles – funkce
V daném seznamu místních souborů, tato funkce určuje soubory, které se liší od odpovídající verze v databázi správy zdrojového kódu.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccEnumChangedFiles(  
   LPVOID  pContext,  
   HWND    hWnd,  
   LONG    cFiles,  
   LPCSTR* lpFileNames,  
   LONG*   plIsFileDifferent  
);  
```  
  
### <a name="parameters"></a>Parametry  
 pContext  
 [in] Ukazatel kontext modulu plug-in zdroje ovládacího prvku.  
  
 hWnd  
 [in] Popisovač okna integrovaného vývojového prostředí, které modul plug-in správy zdrojového kódu můžete použít jako nadřazený pro všechna dialogová okna, které poskytuje.  
  
 cFiles  
 [in] Počet názvů souborů podle `lpFileNames` pole. Také určuje velikost `plIsFileDifferent` pole.  
  
 lpFileNames  
 [in] Pole názvy místních souborů ke kontrole.  
  
 plIsFileDifferent  
 [out v] Pole hodnot, které ukazuje rozdíl stav každého souboru (pole musí mít alespoň `cFiles` položky). Nenulový znamená, že soubor je rozdílný.  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Operace byla úspěšně dokončena.|  
|SCC_UNSPECIFIEDERROR|Obecná chyba.|  
  
## <a name="see-also"></a>Viz také:  
 [Funkce modulu plug-in API zdrojového ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)