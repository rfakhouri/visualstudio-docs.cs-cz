---
title: Funkce SccEndBatch | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- SccEndBatch
helpviewer_keywords:
- SccEndBatch function
ms.assetid: 100e7833-fe0a-45c0-9fca-3e61fd1165b7
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ec549b5bb0a6c48946edf59f0ab1423cea0ac704
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="sccendbatch-function"></a>SccEndBatch – funkce
Tato funkce se ukončí dávku operace zdroj ovládacího prvku. Tyto dávek nelze vnořit.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccEndBatch(void);  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Dávkové operace úspěšně uzavřena.|  
|SCC_E_UNKNOWNERROR|Došlo k nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Zdroj ovládacího prvku dávky se používá k provedení stejné operace zdroj ovládacího prvku napříč více projektů nebo více kontextů. K vyloučení redundantní dialogová okna z činnost koncového uživatele během dávkové operace můžete použít dávky. [SccBeginBatch](../extensibility/sccbeginbatch-function.md) a `SccEndBatch` funkce se používají jako dvojice označující začátek a konec operace. Nemůže být vnořena.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [SccBeginBatch](../extensibility/sccbeginbatch-function.md)