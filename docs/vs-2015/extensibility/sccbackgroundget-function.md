---
title: Sccbackgroundget – funkce | Dokumentace Microsoftu
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: reference
f1_keywords:
- SccBackgroundGet
helpviewer_keywords:
- SccBackgroundGet function
ms.assetid: 69817e52-b9ac-4f4d-820b-2cc9c384f0dc
caps.latest.revision: 14
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 118d8458fd9581a87baea08452d0011d4d66c9a1
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63432475"
---
# <a name="sccbackgroundget-function"></a>SccBackgroundGet – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Tato funkce se načte ze správy zdrojového kódu každého ze zadaných souborů bez zásahu uživatele.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccBackgroundGet(  
   LPVOID  pContext,  
   LONG    nFiles,  
   LPCSTR* lpFileNames,  
   LONG    dwFlags,  
   LONG    dwBackgroundOperationID  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 pContext  
 [in] Ukazatel kontext modulu plug-in zdroje ovládacího prvku.  
  
 %{nfiles/  
 [in] Počet souborů podle `lpFileNames` pole.  
  
 lpFileNames  
 [out v] Pole názvy souborů, které se mají načíst.  
  
> [!NOTE]
> Názvy musí být plně kvalifikovaný místní názvy souborů.  
  
 dwFlags  
 [in] Příkaz příznaky (`SCC_GET_ALL`, `SCC_GET_RECURSIVE`).  
  
 dwBackgroundOperationID  
 [in] Jedinečná hodnota přidružená k této operaci.  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Operace byla úspěšně dokončena.|  
|SCC_E_BACKGROUNDGETINPROGRESS|Načítání na pozadí již probíhá (modul plug-in správy zdrojového kódu by měla vrátit to jenom v případě, že nepodporuje souběžné dávkové operace).|  
|SCC_I_OPERATIONCANCELED|Operace byla zrušena před probíhá její dokončování.|  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce je volána vždy ve vlákně, která se liší od toho, který načten modul plug-in správy zdrojového kódu. Tato funkce se má vracet, dokud se provádí; může být však volána více než jednou s více seznamů soubory, všechny najednou.  
  
 Použití `dwFlags` argument je stejné jako [sccget –](../extensibility/sccget-function.md).  
  
## <a name="see-also"></a>Viz také  
 [Funkce rozhraní API modulu Plug-in zdroje ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)   
 [SccGet](../extensibility/sccget-function.md)
