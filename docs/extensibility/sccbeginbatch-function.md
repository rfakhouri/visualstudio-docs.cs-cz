---
title: Funkce SccBeginBatch | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SccBeginBatch
helpviewer_keywords:
- SccBeginBatch function
ms.assetid: 33968183-2e15-4e0d-955b-ca12212d1c25
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: d6415953a350321cb13f2705fa2bb182c278faa3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="sccbeginbatch-function"></a>SccBeginBatch – funkce
Tato funkce spustí batch posloupnost operací se zdrojovým ovládacího prvku. [SccEndBatch](../extensibility/sccendbatch-function.md) bude volána k ukončení dávky. Tyto dávek nelze vnořit.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
SCCRTN SccBeginBatch(void);  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="return-value"></a>Návratová hodnota  
 Očekává se, že modul plug-in implementace zdroje řízení této funkce vrátí jednu z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Dávkové operace úspěšně začalo.|  
|SCC_E_UNKNOWNERROR|Došlo k nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Zdroj ovládacího prvku dávky se používá k provedení stejné operace napříč více projektů nebo více kontextů. K vyloučení dialogová okna redundantní projekt z činnost koncového uživatele během dávkové operace můžete použít dávky. `SccBeginBatch` Funkce a [SccEndBatch](../extensibility/sccendbatch-function.md) se používají jako dvojice funkce označující začátek a konec operace. Nemůže být vnořena. `SccBeginBatch`Nastaví příznak označující, že dávkové operace probíhá.  
  
 Během dávkové operace je platná, modul plug-in zdrojového kódu by měla poskytnout maximálně jeden dialogové okno pro všechny otázky, které uživateli a použít odpověď z toto okno zobrazené na všechny následné operace.  
  
## <a name="see-also"></a>Viz také  
 [Funkce modulu Plug-in rozhraní API ovládacího prvku zdroje](../extensibility/source-control-plug-in-api-functions.md)   
 [SccEndBatch](../extensibility/sccendbatch-function.md)