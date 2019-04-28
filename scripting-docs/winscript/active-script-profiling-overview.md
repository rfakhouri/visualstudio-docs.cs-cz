---
title: Přehled profilace aktivních skriptů | Dokumentace Microsoftu
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Active Script Profiling
ms.assetid: eec2f413-6605-4df4-a86f-4919755e9358
caps.latest.revision: 10
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 777d20ecb51b09b282f88dc08464727b9ff2a945
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/23/2019
ms.locfileid: "63432980"
---
# <a name="active-script-profiling-overview"></a>Přehled profilace aktivních skriptů
[Aktivní rozhraní Profiler skriptů](../winscript/reference/active-script-profiler-interfaces.md) povolit profilaci skriptovací stroje. Aktivní profilace skriptu se skládá z následujících částí:  
  
- Modul jazyka  
  
- Hostitel  
  
- profiler  
  
## <a name="language-engine"></a>Modul jazyka  
 Modul jazyka spustí skript. Poskytuje metody, které umožní profilování kód skriptu, jak se spouští. Když je povolená profilace, jazyk modul přijímá identifikátor třídy (CLSID) profileru objekt modelu COM jako argument. Vytvoří instanci objektu COM profileru a pak zavolá do profileru, pokud dojde k různým událostem.  
  
 Implementuje modul jazyka [iactivescriptprofilercontrol – rozhraní](../winscript/reference/iactivescriptprofilercontrol-interface.md).  
  
> [!NOTE]
> [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] CLR kontroluje JS_PROFILER proměnnou prostředí při vytváření k určení, zda by měla být povolená profilace. Pokud tato proměnná je nastavena na identifikátor CLSID profileru, modul runtime jazyka vytvoří instanci objektu COM profileru, použití hodnotu proměnné k určení, které profileru, chcete-li vytvořit.  
  
## <a name="host"></a>Hostitel  
 Hostitel vytvoří modul jazyka a poskytuje modul jazyka pomocí skriptů, které má být proveden. Inteligentního hostitele také poskytuje kontext dokumentu, který je možné poskytovat lepší informace při ladění nebo profilování pomocí ladicího programu a profileru.  
  
## <a name="profiler"></a>profiler  
 Pokud dojde k různým událostem profiler obdrží volání z modulu jazyka. Profiler musí být registrován jako objekt modelu COM a musí implementovat [iactivescriptprofilercallback – rozhraní](../winscript/reference/iactivescriptprofilercallback-interface.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní profileru aktivních skriptů](../winscript/reference/active-script-profiler-interfaces.md)