---
title: Sccbeginbatch – funkce | Dokumentace Microsoftu
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
- SccBeginBatch
helpviewer_keywords:
- SccBeginBatch function
ms.assetid: 33968183-2e15-4e0d-955b-ca12212d1c25
caps.latest.revision: 15
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: e62074fa30d68e4cd283fb431f0ae64cff957ed4
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 08/22/2018
ms.locfileid: "42669420"
---
# <a name="sccbeginbatch-function"></a>SccBeginBatch – funkce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Nejnovější verzi tohoto tématu můžete najít v [sccbeginbatch – funkce](https://docs.microsoft.com/visualstudio/extensibility/sccbeginbatch-function).  
  
Tato funkce spustí batch posloupnost operací správy zdrojů. [Sccendbatch –](../extensibility/sccendbatch-function.md) bude volána k ukončení služby batch. Tyto dávek nemůže být vnořený.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp#  
SCCRTN SccBeginBatch(void);  
```  
  
#### <a name="parameters"></a>Parametry  
 Žádné  
  
## <a name="return-value"></a>Návratová hodnota  
 Modul plug-in implementaci ovládacího prvku zdroje této funkce má vracet instanci jednoho z následujících hodnot:  
  
|Hodnota|Popis|  
|-----------|-----------------|  
|SCC_OK|Dávkové operace úspěšně začala.|  
|SCC_E_UNKNOWNERROR|K nespecifikované chybě.|  
  
## <a name="remarks"></a>Poznámky  
 Zdrojový ovládací prvek dávky se používají ke spouštění stejné operace napříč více projektů nebo několika kontextech. Dávky je možné vyloučit redundantní jednotlivých projektů dialogových oknech uživatelským prostředím během dávkové operace. `SccBeginBatch` Funkce a [sccendbatch –](../extensibility/sccendbatch-function.md) slouží jako dvojice funkce označuje začátek a konec operace. Nemůže být vnořený. `SccBeginBatch` Nastaví příznak označující, že dávkové operace probíhá.  
  
 Dávkové operace je v platnosti, by měl modul plug-in správy zdrojového kódu prezentovat maximálně jeden dialogové okno pro každou otázku uživateli a použít na všechny následné operace odpovědi z tohoto dialogového okna.  
  
## <a name="see-also"></a>Viz také  
 [Funkce rozhraní API modulu Plug-in zdroje ovládacího prvku](../extensibility/source-control-plug-in-api-functions.md)   
 [Sccendbatch –](../extensibility/sccendbatch-function.md)

