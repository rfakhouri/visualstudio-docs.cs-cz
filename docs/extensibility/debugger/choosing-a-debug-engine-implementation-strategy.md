---
title: Výběr strategie implementace modulu ladění | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, implementation strategies
ms.assetid: 90458fdd-2d34-4f10-82dc-6d8f31b66d8b
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3c3715bac00b25cd2080a1162c8e2ce8cb33e63a
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 04/16/2018
---
# <a name="choosing-a-debug-engine-implementation-strategy"></a>Výběr strategie implementace modulu ladění
Architektura běhu použijte k určení strategie implementace ladění modulu (DE). Modul ladění mohou být vytvořeny v rámci procesu pro program, který má být vyladěnou, v rámci procesu sadě Visual Studio relace ladění manager (SDM) nebo mimo proces do obou z nich. Následující pokyny by měly pomoci vám vybrat mezi tyto tři strategie.  
  
## <a name="guidelines"></a>Pokyny  
 Když je možné pro DE být mimo proces SDM i program chcete ladit, obvykle neexistuje žádný důvod k tomu. Volání přes hranice procesu jsou relativně pomalé.  
  
 Ladění moduly jsou už zadané pro prostředí Win32 nativní run-time a běžné prostředí runtime jazyka. Pokud pro některou z těchto prostředí musí nahradit DE, je nutné vytvořit DE v rámci procesu s SDM.  
  
 Jinak můžete zvolit vytváření DE v procesu na SDM nebo v rámci procesu programu chcete ladit. Je důležité zvážit, jestli vyhodnocovací filtr výrazů z DE potřebuje rychlosti přístupu k úložišti symbol program a jestli úložiště symbolů může být načtena do paměti pro rychlý přístup. Zvažte také následující:  
  
-   Pokud nejsou k dispozici mnoho volání mezi vyhodnocovací filtr výrazů a úložiště symbolů, nebo pokud úložiště symbolů lze číst do paměťového prostoru SDM, vytvořte DE v proces SDM. Musíte se vrátit CLSID ladění stroje do SDM při připojování do vaší aplikace. SDM používá k vytvoření instance v procesu DE tento CLSID.  
  
-   Pokud je DE musí volat program, který má přístup k úložišti symbol, vytvořte DE v rámci procesu s programu. V takovém případě program vytvoří instanci DE.  
  
## <a name="see-also"></a>Viz také  
 [Rozšiřitelnost programu Visual Studio Debugger](../../extensibility/debugger/visual-studio-debugger-extensibility.md)