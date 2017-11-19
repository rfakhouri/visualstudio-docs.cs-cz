---
title: Funkce SccBackgroundGet | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SccBackgroundGet
helpviewer_keywords: SccBackgroundGet function
ms.assetid: 69817e52-b9ac-4f4d-820b-2cc9c384f0dc
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 85b700f0cb1e3a364cae69ff6c628151ea6a7bd3
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/31/2017
---
# <a name="sccbackgroundget-function"></a>SccBackgroundGet – funkce
Tato funkce načte od správy zdrojového kódu každé zadané soubory bez zásahu uživatele.  
  
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
 [v] Ukazatel modulu plug-in kontextu zdroj ovládacího prvku.  
  
 : %{nfiles/  
 [v] Počet souborů zadaný v `lpFileNames` pole.  
  
 lpFileNames  
 [ve out] Pole názvy souborů, které mají být načteny.  
  
> [!NOTE]
>  Názvy musí být plně kvalifikovaný místní názvy souborů.  
  
 dwFlags  
 [v] Příkaz příznaky (`SCC_GET_ALL`, `SCC_GET_RECURSIVE`).  
  
 dwBackgroundOperationID  
 [v] Jedinečnou hodnotu související s touto operací.  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Operace byla úspěšně dokončena.|  
|SCC_E_BACKGROUNDGETINPROGRESS|Načtení pozadí již probíhá (modul plug-in zdrojového kódu by měla vrátit to jenom v případě, že nepodporuje souběžné dávkových operací).|  
|SCC_I_OPERATIONCANCELED|Operace byla zrušena před jeho dokončení.|  
  
## <a name="remarks"></a>Poznámky  
 Tato funkce je volána vždy na jiného vlákna než ten, který načíst modul plug-in zdrojového kódu. Tato funkce není očekáván vrátit až poté, co; může být však volána vícekrát s více seznamů souborů, všechny ve stejnou dobu.  
  
 Použití `dwFlags` argument je stejný jako [SccGet](../extensibility/sccget-function.md).  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [SccGet](../extensibility/sccget-function.md)