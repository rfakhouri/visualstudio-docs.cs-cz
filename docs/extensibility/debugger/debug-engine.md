---
title: Ladicí stroj | Dokumentace Microsoftu
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- debug engines
ms.assetid: 148b1efc-ca07-4d8e-bdfc-c723a760c620
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5f4852556b7938b6e017edc94ddb88ee0267e699
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/25/2019
ms.locfileid: "55033450"
---
# <a name="debug-engine"></a>Ladicí stroj
Ladicí stroj (DE) funguje překladač nebo operačního systému k poskytování služeb ladění, jako je například ovládací prvek, zarážky a výraz zkušební spuštění. DE je zodpovědný za monitorování stavu programu, který se právě ladí. K tomu používá DE jakékoli metody jsou k dispozici v modulu runtime podporované, jestli z procesoru nebo z rozhraní API poskytovaných modulu runtime.  
  
 Například common language runtime (CLR) poskytuje mechanismus pro monitorování spuštěný program prostřednictvím rozhraní ICorDebugXXX. DE, který podporuje modul CLR použije příslušné rozhraní ICorDebugXXX ke sledování laděného programu spravovaného kódu. Potom komunikuje změny stavu pro správce ladění relace (SDM), která předá tyto informace [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] integrovaného vývojového prostředí.  
  
> [!NOTE]
>  Ladicí stroj cílí na konkrétního modulu runtime, to znamená, ve kterém program laděn spuštění systému. Modul CLR je modul runtime pro spravovaný kód a modul runtime Win32 je pro nativní aplikace pro Windows. Pokud vytvoříte jazyk můžete cílit na jednu z těchto dvou modulů runtime, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] již poskytuje nezbytné ladicí stroj. Vše, co máte k implementaci je vyhodnocovače výrazů.  
  
## <a name="debug-engine-operation"></a>Ladění modulu operace  
 Monitorování služby jsou implementované pomocí rozhraní DE a může způsobit, že balíček ladění pro přechod mezi různé provozní režimy. Další informace najdete v tématu [provozní režimy](../../extensibility/debugger/operational-modes.md). Obvykle existuje pouze jedna implementace DE pro každé prostředí za běhu.  
  
> [!NOTE]
>  I když existují samostatné implementace DE příkazů jazyka Transact-SQL a [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)], VBScript a [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)] sdílet jeden DE.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění umožňuje ladit stroje pro spuštění jedním ze dvou způsobů: buď ve stejném procesu jako [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] prostředí, nebo právě laděny ve stejném procesu jako cílového programu. Druhý formulář obvykle dochází, když se v laděném procesu je ve skutečnosti skript spuštěn pod interpretu. Ladicí stroj musí mít dokonalou znalost interpretu pro monitorování skriptu. V takovém případě interpretu je ve skutečnosti modul runtime; ladicí stroj jsou pro implementace modulu runtime specifické. Kromě toho je možné rozdělit provádění jedné DE přes hranice procesu a strojově (například vzdálené ladění).  
  
 Zpřístupňuje DE [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ladění v rozhraní. Veškerá komunikace je pomocí modelu COM. Zda DE je načten v procesu, out-of-process nebo na jiném počítači, neovlivní komunikace komponent.  
  
 DE spolupracuje komponenty Chyba při vyhodnocování výrazu DE pro tento konkrétní runtime k pochopení syntaxe výrazů. DE funguje taky s komponentou obslužné rutiny symbolů pro přístup k symbolické ladicí informace generované kompilátorem jazyka. Další informace najdete v tématu [vyhodnocovací filtr výrazů](../../extensibility/debugger/expression-evaluator.md) a [poskytovatel symbolů](../../extensibility/debugger/symbol-provider.md).  
  
## <a name="see-also"></a>Viz také:  
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)   
 [Chyba při vyhodnocování výrazu](../../extensibility/debugger/expression-evaluator.md)   
 [Poskytovatel symbolů](../../extensibility/debugger/symbol-provider.md)