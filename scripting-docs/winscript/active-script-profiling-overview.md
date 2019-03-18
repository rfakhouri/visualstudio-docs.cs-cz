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
ms.openlocfilehash: d03ab4df7a41fe6513a18446d26e33e9856d1183
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/18/2019
ms.locfileid: "58149611"
---
# <a name="active-script-profiling-overview"></a>Přehled profilace aktivních skriptů
[Aktivní rozhraní Profiler skriptů](../winscript/reference/active-script-profiler-interfaces.md) povolit profilaci skriptovací stroje. Aktivní profilace skriptu se skládá z následujících částí:  
  
-   Modul jazyka  
  
-   Hostitel  
  
-   profiler  
  
## <a name="language-engine"></a>Modul jazyka  
 Modul jazyka spustí skript. Poskytuje metody, které umožní profilování kód skriptu, jak se spouští. Když je povolená profilace, jazyk modul přijímá identifikátor třídy (CLSID) profileru objekt modelu COM jako argument. Vytvoří instanci objektu COM profileru a pak zavolá do profileru, pokud dojde k různým událostem.  
  
 Implementuje modul jazyka [iactivescriptprofilercontrol – rozhraní](../winscript/reference/iactivescriptprofilercontrol-interface.md).  
  
> [!NOTE]
>  [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] CLR kontroluje JS_PROFILER proměnnou prostředí při vytváření k určení, zda by měla být povolená profilace. Pokud tato proměnná je nastavena na identifikátor CLSID profileru, modul runtime jazyka vytvoří instanci objektu COM profileru, použití hodnotu proměnné k určení, které profileru, chcete-li vytvořit.  
  
## <a name="host"></a>Hostitel  
 Hostitel vytvoří modul jazyka a poskytuje modul jazyka pomocí skriptů, které má být proveden. Inteligentního hostitele také poskytuje kontext dokumentu, který je možné poskytovat lepší informace při ladění nebo profilování pomocí ladicího programu a profileru.  
  
## <a name="profiler"></a>profiler  
 Pokud dojde k různým událostem profiler obdrží volání z modulu jazyka. Profiler musí být registrován jako objekt modelu COM a musí implementovat [iactivescriptprofilercallback – rozhraní](../winscript/reference/iactivescriptprofilercallback-interface.md) rozhraní.  
  
## <a name="see-also"></a>Viz také  
 [Rozhraní profileru aktivních skriptů](../winscript/reference/active-script-profiler-interfaces.md)