---
title: Ladicí stroj | Dokumentace Microsoftu
ms.custom: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- debug engines
ms.assetid: 148b1efc-ca07-4d8e-bdfc-c723a760c620
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 781712ad9ef199073028b62a3fc5a50b4c2cad77
ms.sourcegitcommit: 9ceaf69568d61023868ced59108ae4dd46f720ab
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/12/2018
ms.locfileid: "49282682"
---
# <a name="debug-engine"></a>Ladicí stroj
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Ladicí stroj (DE) funguje překladač nebo operačního systému k poskytování služeb ladění, jako je například ovládací prvek, zarážky a výraz zkušební spuštění. DE je zodpovědný za monitorování stavu programu, který se právě ladí. K tomu používá DE jakékoli metody jsou k dispozici v modulu runtime podporované, jestli z procesoru nebo z rozhraní API poskytovaných modulu runtime.  
  
 Například common language runtime (CLR) poskytuje mechanismus pro monitorování spuštěný program prostřednictvím rozhraní ICorDebugXXX. DE, který podporuje modul CLR použije příslušné rozhraní ICorDebugXXX ke sledování laděného programu spravovaného kódu. Potom komunikuje změny stavu pro správce ladění relace (SDM), která předá tyto informace [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] integrovaného vývojového prostředí.  
  
> [!NOTE]
>  Ladicí stroj cílí na konkrétního modulu runtime, to znamená, ve kterém program laděn spuštění systému. Modul CLR je modul runtime pro spravovaný kód a modul runtime Win32 je pro nativní aplikace pro Windows. Pokud vytvoříte jazyk můžete cílit na jednu z těchto dvou modulů runtime, [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] již poskytuje nezbytné ladicí stroj. Vše, co máte k implementaci je vyhodnocovače výrazů.  
  
## <a name="debug-engine-operation"></a>Ladění modulu operace  
 Monitorování služby jsou implementované pomocí rozhraní DE a může způsobit, že balíček ladění pro přechod mezi různé provozní režimy. Další informace najdete v tématu [provozní režimy](../../extensibility/debugger/operational-modes.md). Obvykle existuje pouze jedna implementace DE pro každé prostředí za běhu.  
  
> [!NOTE]
>  I když existují samostatné implementace DE příkazů jazyka Transact-SQL a [!INCLUDE[jsprjscript](../../includes/jsprjscript-md.md)], VBScript a [!INCLUDE[jsprjscript](../../includes/jsprjscript-md.md)] sdílet jeden DE.  
  
 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladění umožňuje ladit stroje pro spuštění jedním ze dvou způsobů: buď ve stejném procesu jako [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] prostředí, nebo právě laděny ve stejném procesu jako cílového programu. Druhý formulář obvykle dochází, když do něho laděný proces je ve skutečnosti skript spuštěn pod interpretu a ladicí stroj musí znát dokonalou interpretu kvůli monitorování skriptu. Všimněte si, že v tomto případě interpretu je ve skutečnosti modul runtime; ladicí stroj jsou pro implementace modulu runtime specifické. Kromě toho je možné rozdělit provádění jedné DE přes hranice procesu a strojově (například vzdálené ladění).  
  
 Zpřístupňuje DE [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] ladění v rozhraní. Veškerá komunikace je pomocí modelu COM. Zda DE je načten v procesu, out-of-process nebo na jiném počítači, neovlivní komunikace komponent.  
  
 DE spolupracuje komponenty Chyba při vyhodnocování výrazu DE pro tento konkrétní běhu k pochopení syntaxe výrazů. DE funguje taky s komponentou obslužné rutiny symbolů pro přístup k symbolické ladicí informace generované kompilátorem jazyka. Další informace najdete v tématu [vyhodnocovací filtr výrazů](../../extensibility/debugger/expression-evaluator.md) a [poskytovatel symbolů](../../extensibility/debugger/symbol-provider.md).  
  
## <a name="see-also"></a>Viz také  
 [Komponenty ladicího programu](../../extensibility/debugger/debugger-components.md)   
 [Chyba při vyhodnocování výrazu](../../extensibility/debugger/expression-evaluator.md)   
 [Poskytovatel symbolů](../../extensibility/debugger/symbol-provider.md)

