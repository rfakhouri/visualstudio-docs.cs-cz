---
title: Sccbackgroundget – funkce | Dokumentace Microsoftu
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- SccBackgroundGet
helpviewer_keywords:
- SccBackgroundGet function
ms.assetid: 69817e52-b9ac-4f4d-820b-2cc9c384f0dc
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 162bbc427b48ee10ea3a0b88837cf012f1c3fd07
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629240"
---
# <a name="sccbackgroundget-function"></a>SccBackgroundGet – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [sccbackgroundget – funkce](https://docs.microsoft.com/visualstudio/extensibility/sccbackgroundget-function).  
  
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
>  Názvy musí být plně kvalifikovaný místní názvy souborů.  
  
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
 [Sccget –](../extensibility/sccget-function.md)

