---
title: "Ladění modul | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines
ms.assetid: 148b1efc-ca07-4d8e-bdfc-c723a760c620
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 70e572b73f8474f77a17989c790f2e7336f9d7a5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 12/22/2017
---
# <a name="debug-engine"></a>Ladění modulu
Modul ladění (DE) pracuje s překladač nebo operačního systému, k poskytování ladění služby, jako je například spouštění řízení, zarážky a výraz vyhodnocení. DE je odpovědná za monitorování stavu laděné programu. K tomu je DE používá jakékoli metody je dostupné v podporovaných modulu runtime, zda z procesoru nebo z rozhraní API dodané modulem runtime.  
  
 Například modul CLR (CLR) poskytuje mechanismy pro monitorování spuštěným programem prostřednictvím rozhraní ICorDebugXXX. Německo, která podporuje modulu CLR používá rozhraní odpovídající ICorDebugXXX ke sledování laděné program spravovaného kódu. Potom komunikuje změny stavu pro relaci ladění správce (SDM), který předává tyto informace o [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
> [!NOTE]
>  Modul ladění cílí konkrétní modul runtime, to znamená, ve kterém se program ladit spuštění systému. Modul CLR je modul runtime pro spravovaný kód a Win32 runtime je pro nativní aplikace systému Windows. Pokud jazyk vytvoříte, můžete vybrat jednu z těchto dvou runtimes [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] již poskytuje moduly nezbytné ladění. Stačí, abyste pro implementaci je vyhodnocovací filtr výrazů.  
  
## <a name="debug-engine-operation"></a>Ladění modul operace  
 Monitorování služby jsou implementovány pomocí rozhraní DE a může způsobit debug balíček přechod mezi různé režimy provozu. Další informace najdete v tématu [provozní režimy](../../extensibility/debugger/operational-modes.md). Je obvykle pouze jeden implementace DE za běhu prostředí.  
  
> [!NOTE]
>  Přestože jsou samostatné implementace DE Transact-SQL a [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)], VBScript a [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)] sdílet jeden DE.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]ladění umožňuje ladění moduly spustit jedním ze dvou způsobů: buď v rámci jednoho procesu, jako [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostředí shell, nebo v rámci jednoho procesu jako cíl programu laděné. Druhé formuláře obvykle dojde, pokud proces laděné je ve skutečnosti skript spuštěn pod překladač a ladění modul musí mít dokonalou znalosti překladač, aby monitorování skriptu. Všimněte si, že v tomto případě překladač je ve skutečnosti runtime; ladění moduly jsou pro konkrétní runtime implementace. Kromě toho můžete rozdělit provádění jedné DE napříč hranicemi procesů a počítače (například vzdálené ladění).  
  
 DE zpřístupňuje [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění v rozhraní. Veškerá komunikace je prostřednictvím modelu COM. Jestli je DE je zavedený v procesu, mimo proces nebo na jiném počítači, nemá vliv součást komunikace.  
  
 DE pracuje s komponentu vyhodnocování výrazu povolit DE pro tuto konkrétní běhu pochopit syntaxe výrazů. DE taky spolupracuje se službou součást obslužná rutina symbol pro přístup k symbolické ladicí informace generované kompilátor jazyka. Další informace najdete v tématu [vyhodnocovací filtr výrazů](../../extensibility/debugger/expression-evaluator.md) a [Symbol zprostředkovatele](../../extensibility/debugger/symbol-provider.md).  
  
## <a name="see-also"></a>Viz také  
 [Ladicí program komponenty](../../extensibility/debugger/debugger-components.md)   
 [Vyhodnocení výrazu](../../extensibility/debugger/expression-evaluator.md)   
 [Poskytovatel symbolů](../../extensibility/debugger/symbol-provider.md)