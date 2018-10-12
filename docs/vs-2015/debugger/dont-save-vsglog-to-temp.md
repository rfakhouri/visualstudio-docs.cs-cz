---
title: DONT_SAVE_VSGLOG_TO_TEMP | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f27ab0e6-9575-4ca0-9901-37d3e5c3a2f5
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 488baf1b2b01fe1491ccd00247e245e1642424d1
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49200002"
---
# <a name="dontsavevsglogtotemp"></a>DONT_SAVE_VSGLOG_TO_TEMP
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Definuje jeho přítomnost, zda soubor protokolu grafiky je uložen do adresáře dočasných souborů uživatele.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp  
#define DONT_SAVE_VSGLOG_TO_TEMP  
```  
  
## <a name="value"></a>Hodnota  
 Symbol preprocesoru, podle přítomnosti nebo nepřítomnosti Určuje, zda soubor protokolu grafiky je uložen do adresáře dočasných souborů uživatele. Pokud tento symbol je definován, je název souboru určené `VSG_DEFAULT_RUN_FILENAME` je relativní vzhledem k aktuální adresář zachycené aplikace nebo je absolutní cesta; v opačném případě se název souboru určené `VSG_DEFAULT_RUN_FILENAME` je relativní k adresáři dočasné soubory uživatele a nemůže být absolutní cesta.  
  
## <a name="remarks"></a>Poznámky  
 V závislosti na oprávnění uživatele nemusí být možné uložit do libovolného umístění souboru protokolu grafiky. Doporučujeme vám, že chcete uložit protokoly grafiky do adresáře dočasných souborů uživatele nebo jiného umístění známému dobrému, pokud si nejste jisti, zda umístění, na které byste zvolili, je možné zapisovat na uživatelem.  
  
 Chcete-li zabránit souboru protokolu grafiky, neuloží se do adresáře s dočasnými soubory, musí být definován `DONT_SAVE_VSGLOG_TO_TEMP` teprve potom zahrňte `vsgcapture.h`.  
  
## <a name="example"></a>Příklad  
 Tento příklad ukazuje, jak uložit soubor protokolu grafiky na absolutní cestu, na hostitelském počítači.  
  
```  
// Define DONT_SAVE_VSGLOG_TO_TEMP and VSG_DEFAULT_RUN_FILENAME before including vsgcapture.h  
#define DONT_SAVE_VSGLOG_TO_TEMP  
#define VSG_DEFAULT_RUN_FILENAME L"C:\\Graphics Diagnostics Captures\\default.vsglog"  
  
#include <vsgcapture.h>  
  
```  
  
## <a name="see-also"></a>Viz také  
 [VSG_DEFAULT_RUN_FILENAME](../debugger/vsg-default-run-filename.md)



